
# InaSAFE Command Line Interface

[![Build Status](https://travis-ci.org/inasafe/inasafe_cli.svg?branch=master)](https://travis-ci.org/inasafe/inasafe_cli)

This is the command line client implementation for [InaSAFE](http://inasafe.org).

## Installation
1. Install InaSAFE CLI by from pip by running this command:

   ```pip install inasafe-cli```

2. Make sure that your environment has QGIS. You can check if you environment is ready by running this on your python console:

   ```import qgis```

3. Add QGIS python plugin directory into your python path. [See here](https://github.com/inasafe/inasafe/blob/develop/run-env-linux.sh) 
   

## USAGE EXAMPLES
### Showing help

You can type ```inasafe``` or ```inasafe -h``` or ```inasafe --help``` to show how to use this command line

### Showing QGIS and InaSAFE version that is used

```inasafe -v``` or ```inasafe --version```

### Downloading exposures

```inasafe --download --feature-type=buildings --extent=106,84:-6,2085970:106,8525945:-6,1876174 --output-dir=/home/akbar/dev/data/test_cli/```

Feature type can be:
- roads 
- buildings
- building-points 
- potential-idp
- boundary-x (with x from 1 to11)

### Running scenario

When specifying the path to the hazard, exposure, or aggregation file, it can be relative or absolute.

You can run the scenario with extent or (mutually exclusive) with an aggregation layer

- Using extent:

```inasafe --hazard=safe/test/data/gisv4/hazard/tsunami_vector.geojson --exposure=safe/test/data/gisv4/exposure/raster/population.asc  --output-dir=/home/akbar/dev/data/test_cli/ --extent=106,7999364:-6,2085970:106,8525945:-6,1676174```

- Using aggregation layer
```inasafe --hazard=safe/test/data/gisv4/hazard/tsunami_vector.geojson --exposure=safe/test/data/gisv4/exposure/raster/population.asc  --aggregation=safe/test/data/gisv4//aggregation/small_grid_complex.geojson  --output-dir=/home/akbar/dev/data/test_cli/```
