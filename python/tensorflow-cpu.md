# 问题描述
```
raise ValueError("None values not supported.")
ValueError: None values not supported.
```

# 具体
```
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
```

# 解决方法
降级Tensorflow至1.12.0，降级后提示
```
module 'tensorflow.python.keras.backend' has no attribute 'get_graph'
```  
降级Keras至2.2.4.

# 问题续
出现错误提示
```
Traceback (most recent call last):
  File "judger_position_with_context.py", line 121, in <module>
    validation_data=(x_test, y_test), callbacks=[history])
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/keras/engine/training.py", line 1039, in fit
    validation_steps=validation_steps)
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/keras/engine/training_arrays.py", line 199, in fit_loop
    outs = f(ins_batch)
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/keras/backend/tensorflow_backend.py", line 2715, in __call__
    return self._call(inputs)
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/keras/backend/tensorflow_backend.py", line 2675, in _call
    fetched = self._callable_fn(*array_vals)
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/tensorflow/python/client/session.py", line 1439, in __call__
    run_metadata_ptr)
  File "/root/anaconda3/envs/thuys36/lib/python3.6/site-packages/tensorflow/python/framework/errors_impl.py", line 528, in __exit__
    c_api.TF_GetCode(self.status.status))
tensorflow.python.framework.errors_impl.InvalidArgumentError: indices[56,16] = -1 is not in [0, 20)
   [[{{node embedding_2/embedding_lookup}} = GatherV2[Taxis=DT_INT32, Tindices=DT_INT32, Tparams=DT_FLOAT, _class=["loc:@training/Adam/Assign_5"], _device="/job:localhost/replica:0/task:0/device:CPU:0"](embedding_2/embeddings/read, lambda_1/concat, training/Adam/gradients/embedding_2/embedding_lookup_grad/concat/axis)]]
```

# 解决方法
推测是出现了'/xab'之类的被转义的符号？