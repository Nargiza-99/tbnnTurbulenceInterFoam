# trnnTurbulenceInterFoam
Calculation of turbulence two-phase flow using interFoam solver & calculation of basis tensors and their invariants for future modelling of turbulent terms arising from Reynolds averaging.

## Requirements
1. OpenFOAM
2. tensorflow c api
( you can find installation guide here: https://www.tensorflow.org/install/lang_c )

## Note
1. Works correctly only when executed single-threaded (Multi-threaded execution is not supported!)
2. The pressure field (p_rgh) is only available from the current time step
3. The trained neural network must be stored in saved_model format
4. To find out the names of the neural network inputs and outputs, just run the following command:
```
model_path = "/path/to/your/model/in/saved_model/format/"
loaded_model = tf.keras.models.load_model(model_path)
loaded_model.summary()
