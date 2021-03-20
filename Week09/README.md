lightgbm 原始数据，调参后accuracy_score：0.91854

删除一组特征：'discrete_term_1_one_hot','discrete_home_ownership_1_one_hot','discrete_purpose_1_one_hot'，调参后accuracy_score：0.91856

删除第二组特征：'continuous_pub_rec','continuous_dti_joint'，调参后accuracy_score：0.92246，有所提升。

新增三个衍生变量：
  1. continuous_funded_amnt - continuous_funded_amnt_inv
  2. continuous_mths_since_last_record / continuous_mths_since_last_major_derog
  3. continuous_installment * 12 / continuous_annual_inc

不删除特征的情况下，调参后accuracy_score：0.92284，有明显提升

组合删除两组特征并增加三个衍生变量，调参后accuracy_score：0.92302
