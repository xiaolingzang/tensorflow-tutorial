LSTM 前向传播
-------
## LSTM结构初始化
```
lstm=rnn_cell.BasicLSTMCell(lstm_hidden_size)
```

## LSTM中的状态初始化为0数组
```
staet=lstm.zero_state(batch_szie,tf.float32)
```
## 定义损失函数
```
loss=0
```
## 前向传播
```
for i in range(num_steps):
    if i>0: tf.get_variable_scope().reuse_variables()
    
    lstm_output,state=lstm(current_input,state)
    final_output=fully_connected(lstm_output)
    loss +=calc_loss(final_output,expected_output)
    
```
