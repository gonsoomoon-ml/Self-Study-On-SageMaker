# Vision : Self-Study-On-SageMaker

**마지막 업데이트: 2022.09.13**


---

# 1. Workshop

SageMaker End to End Computer Vision Workshop (Sep 2022)

* https://catalog.us-east-1.prod.workshops.aws/workshops/4dde7f9d-39e8-47b3-89ed-e1c678be6783/en-US



# 2. 유용한 코드


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