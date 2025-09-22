
# TensorFlow/Keras Model Saving and Loading

## 1. Saving a Model in TensorFlow SavedModel Format

**Explanation**  
- **SavedModel** is TensorFlow’s default format.  
- Saves model architecture, weights, and training configuration.  
- Creates a folder instead of a single file.  

**Syntax**
```python
model.save('path/to/save_model')
```

**Example**
```python
import tensorflow as tf
from tensorflow import keras
from tensorflow.keras import layers

# Create a simple model
model = keras.Sequential([
    layers.Dense(64, activation='relu', input_shape=(100,)),
    layers.Dense(10, activation='softmax')
])

# Compile the model
model.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])

# Save in SavedModel format
model.save('saved_model/my_model')
```

**Output Structure**
```
saved_model/
    my_model/
        assets/
        variables/
        saved_model.pb
```

---

## 2. Saving a Model in HDF5 Format

**Explanation**  
- **HDF5** stores the model in a single `.h5` file.  
- Good for sharing and compatibility with older Keras versions.  

**Syntax**
```python
model.save('path/to/model.h5')
```

**Example**
```python
# Save in HDF5 format
model.save('my_model.h5')
```

---

## 3. Loading a Model in TensorFlow SavedModel Format

**Syntax**
```python
model = tf.keras.models.load_model('path/to/saved_model_directory')
```

**Example**
```python
import tensorflow as tf
from tensorflow import keras
import numpy as np

# Load model
model = keras.models.load_model('saved_model/my_model')

# Check model
model.summary()

# Predict
sample_input = np.random.random((1, 100))
prediction = model.predict(sample_input)
print("Prediction:", prediction)
```

---

## 4. Loading a Model in HDF5 Format

**Syntax**
```python
model = tf.keras.models.load_model('path/to/model.h5')
```

**Example**
```python
import tensorflow as tf
from tensorflow import keras
import numpy as np

# Load model
model = keras.models.load_model('my_model.h5')

# Check model
model.summary()

# Predict
sample_input = np.random.random((1, 100))
prediction = model.predict(sample_input)
print("Prediction:", prediction)
```

---

## 5. Summary Table

| Task  | SavedModel Format (Folder)                            | HDF5 Format (.h5 file)                    |
|-------|-------------------------------------------------------|-------------------------------------------|
| Save  | `model.save('saved_model/my_model')`                   | `model.save('my_model.h5')`               |
| Load  | `keras.models.load_model('saved_model/my_model')`      | `keras.models.load_model('my_model.h5')`  |
| Output| Folder with assets, variables, `.pb` file              | Single `.h5` file                         |
