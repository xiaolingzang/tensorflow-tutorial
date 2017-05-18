### TFRecord格式介绍
-----------------------
TensorFlow提供了TFRecord的格式统一存储数据。TFRecord文件中的数据通过```tf.train.Example``` protocol Buffer的格式存储，下面是tf.train.Example的定义。   
```
message Example{
Features features =1;
};
message Features{
map<string,Feature> feature=1;
};
message Feature{
oneof kind{
  BytesList bytes_list=1;
  FloatList float_list=2;
  Int64List int64_list=3;
  }
};
```
tf.train.Example中包含一个从属性名称到取值的字典。其中属性名称为一个字符串，属性的取值可以为字符串(BytesList),实数列表(FloatList),或者整数列表(Int64List)
