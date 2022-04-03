# Vision 주요 참고 문서

**마지막 업데이트: 2022.04.03**


---

#  작업 중 입니다.


```python

- NP Array, Byte Array 를 서로 바꾸는 함수 임

def validate_convert_byte_np(np_arr, shape):
    '''
    Usage:
    import numpy as np    
    i = np.arange(28*28).reshape(28, 28)
    validate_convert_byte_np(i, shape=i.shape)
    
    Convert Byte Array to Numpy Array and vice versa:
        https://stackoverflow.com/questions/53376786/convert-byte-array-back-to-numpy-array
    '''
    byte_arr = np_arr.tobytes()
    y = np.frombuffer(byte_arr, dtype=np_arr.dtype)    
    print("y shape: ", y.shape)
    val = np.array_equal(y.reshape(*shape), np_arr)    
    print("validation: ", val)
    print(y.reshape(*shape).shape)

```