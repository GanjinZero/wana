# 问题描述
raise ValueError("None values not supported.")
ValueError: None values not supported.

# 具体
None
Traceback (most recent call last):
  File "judger_position_with_context.py", line 118, in <module>
    validation_data=(x_test, y_test), callbacks=[history])
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/keras/engine/training.py", line 1213, in fit
    self._make_train_function()
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/keras/engine/training.py", line 316, in _make_train_function
    loss=self.total_loss)
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/keras/legacy/interfaces.py", line 91, in wrapper
    return func(*args, **kwargs)
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/keras/optimizers.py", line 543, in get_updates
    p_t = p - lr_t * m_t / (K.sqrt(v_t) + self.epsilon)
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/tensorflow/python/ops/math_ops.py", line 888, in binary_op_wrapper
    y, dtype_hint=x.dtype.base_dtype, name="y")
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/tensorflow/python/framework/ops.py", line 1145, in convert_to_tensor_v2
    as_ref=False)
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/tensorflow/python/framework/ops.py", line 1224, in internal_convert_to_tensor
    ret = conversion_func(value, dtype=dtype, name=name, as_ref=as_ref)
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/tensorflow/python/framework/constant_op.py", line 305, in _constant_tensor_conversion_function
    return constant(v, dtype=dtype, name=name)
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/tensorflow/python/framework/constant_op.py", line 246, in constant
    allow_broadcast=True)
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/tensorflow/python/framework/constant_op.py", line 284, in _constant_impl
    allow_broadcast=allow_broadcast))
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/tensorflow/python/framework/tensor_util.py", line 454, in make_tensor_proto
    raise ValueError("None values not supported.")
ValueError: None values not supported.
