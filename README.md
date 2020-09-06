# xarray-iris-coord-system
Python class to fix xarray-iris coord_system issue

# Setup
1. Clone this repo
2. Instantiate a class as follows:
```python
from xarray_iris_coord_system import XarrayIrisCoordSystem as xics

xi = xics()
```

3. Use the following methods to convert a `Cube` to a `DataArray` and back that preserves the `coord_system` of the `Cube`:
```python
da = xi.from_iris(cube)

cube = xi.to_iris(da)
```

# Reference
This code was developed to address the issue that Xarray's [`to_iris()`](https://github.com/pydata/xarray/blob/dc2dd89b999b16e08ba51e9cf623896b01be7297/xarray/convert.py#L170) and [`from_iris()`](https://github.com/pydata/xarray/blob/dc2dd89b999b16e08ba51e9cf623896b01be7297/xarray/convert.py#L246) methods don't preserve the `coord_system` of the original Iris `Cube`.
