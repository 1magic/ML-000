删除变量：
 ```'discrete_term_1_one_hot','discrete_home_ownership_1_one_hot','discrete_purpose_1_one_hot'```


增加衍生变量:
   ```
   train_n5['diff_funded_amt'] = train_n5['continuous_funded_amnt'] - train_n5['continuous_funded_amnt_inv']
   test_n5['diff_funded_amt'] = test_n5['continuous_funded_amnt'] - test_n5['continuous_funded_amnt_inv']

   train_n5['division_continuous_mths_since'] = train_n5['continuous_mths_since_last_record'] / train_n5['continuous_mths_since_last_major_derog']
   test_n5['division_continuous_mths_since'] = test_n5['continuous_mths_since_last_record'] / test_n5['continuous_mths_since_last_major_derog']

   train_n5['rate_inst_inc'] = train_n5['continuous_installment']*12 / train_n5['continuous_annual_inc']
   test_n5['rate_inst_inc'] = test_n5['continuous_installment']*12 / test_n5['continuous_annual_inc']
   
   ```
   
stacking集成，采用lightgbm、xgboost、rf分别获取其最佳参数，并对结果进行加权平均输出。
    
