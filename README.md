Here's how to run my code. It took me 25 minutes to refactor my_happy_script.R and write this README.

```r
raw_results_csv <- '1_fetch/out/model_RMSEs.csv'

source('1_fetch/src/fetch_mendota_data.R')
download_mendota_RMSEs(raw_results_csv)

source('2_process/src/assess_model_results.R')
eval_data <- summarize_model_results(raw_results_csv)
write_model_summary_results(eval_data, '2_process/out/model_summary_results.csv')
write_results_assessment(eval_data, assessment_txt='2_process/out/model_diagnostic_text.txt')

source('3_visualize/src/plot_results.R')
plot_pgdl_awesomeness(eval_data, png_file='3_visualize/out/figure_1.png')
```

