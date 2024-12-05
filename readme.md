import java.io.IOException;
import java.util.StringTokenizer;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;

public class EvenOdd {

    public static class TokenizeMapper
            extends Mapper<Object, Text, Text, Text> {

        private Text evenOddKey = new Text();
        private Text numberValue = new Text();

        @Override
        protected void map(Object key, Text value, Context context)
                throws IOException, InterruptedException {
            StringTokenizer itr = new StringTokenizer(value.toString());
            while (itr.hasMoreTokens()) {
                String numStr = itr.nextToken();
                int num = Integer.parseInt(numStr);
                if (num % 2 == 0) {
                    evenOddKey.set("Even");
                } else {
                    evenOddKey.set("Odd");
                }
                numberValue.set(numStr);
                context.write(evenOddKey, numberValue);
            }
        }
    }

    public static class EvenOddReducer
            extends Reducer<Text, Text, Text, Text> {

        private Text result = new Text();

        @Override
        protected void reduce(Text key, Iterable<Text> values, Context context)
                throws IOException, InterruptedException {
            StringBuilder expression = new StringBuilder();
            int sum = 0;

            for (Text val : values) {
                int num = Integer.parseInt(val.toString());
                if (expression.length() > 0) {
                    expression.append(" + ");
                }
                expression.append(num);
                sum += num;
            }
            String formattedOutput = String.format("Sum of %s Numbers: %s = %d",
                    key.toString(), expression.toString(), sum);
            result.set(formattedOutput);
            context.write(null, result); // Use null key for a clean output.
        }
    }

    public static void main(String[] args) throws Exception {
        Configuration conf = new Configuration();
        Job job = Job.getInstance(conf, "Even Odd");

        job.setJarByClass(EvenOdd.class);
        job.setMapperClass(TokenizeMapper.class);
        job.setReducerClass(EvenOddReducer.class);

        job.setOutputKeyClass(Text.class);
        job.setOutputValueClass(Text.class);

        FileInputFormat.addInputPath(job, new Path(args[0]));
        FileOutputFormat.setOutputPath(job, new Path(args[1]));

        System.exit(job.waitForCompletion(true) ? 0 : 1);
    }
}
