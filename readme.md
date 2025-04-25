# Python Utility Scripts

A collection of Python scripts designed for data transformation and generation tasks. Each script performs a specific function, mostly related to data processing, pattern generation, or applying mathematical transformations.

# Requirements

This scripts depends on numpy to make them work, please, follow those steps

```bash
python -m pip install numpy venv
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

# Scripts Overview

## clamir-network-ip-apply

Apply an ip address to the network

```
usage: clamir-network-ip-apply [-h] [-f FILE] [-d DEV]

options:
  -h, --help       show this help message and exit
  -f, --file FILE  config file to be applied
  -d, --dev DEV    device
```

## clamir-scc-util-convert-table

Converts a table from one format to another basically, converts from *.nuc table to *dat usable by the clamir service daemon. Likely supports the nuc binary format. Useful for data preprocessing or adapting data for specific tools.

```
usage: clamir-scc-util-convert-table [-h] [-t TYPE] [-i INPUT] [-o OUTPUT]

options:
  -h, --help           show this help message and exit
  -t, --type TYPE      input type
  -i, --input INPUT    input file
  -o, --output OUTPUT  output file
```

## clamir-scc-util-generate-pattern

Generates a sequence or dataset based on a repeating or custom pattern. Could be used for test data, simulations, or templated data structures.

```
usage: clamir-scc-util-generate-pattern [-h] [-v VALUE] [-o OUTPUT]

options:
  -h, --help           show this help message and exit
  -v, --value VALUE    value
  -o, --output OUTPUT  output file
```

## clamir-scc-util-generate-sequence

```
usage: clamir-scc-util-generate-sequence [-h] [-v VALUE] [-o OUTPUT]

options:
  -h, --help           show this help message and exit
  -v, --value VALUE    value
  -o, --output OUTPUT  output file
```

Creates a numerical or alphanumerical sequence. Ideal for generating index lists, time series data, or batch naming.

## clamir-scc-util-apply-offset

Generates data points uniformly, possibly random values over a specified range or grid. Suitable for simulations, statistical testing, or spatial data.

```
usage: clamir-scc-util-apply-offset [-h] [-v VALUE] [-o OFFSET]

options:
  -h, --help           show this help message and exit
  -v, --value VALUE    value
  -o, --offset OFFSET  address offset
```

## clamir-scc-util-apply-offset-file

Applies an offset to a dataset (e.g., shifting values by a constant). Likely works with piped input or inline values.

```
usage: clamir-scc-util-apply-offset-file [-h] [-i INPUT] [-o OFFSET]

options:
  -h, --help           show this help message and exit
  -i, --input INPUT    input file
  -o, --offset OFFSET  address offset
```

## clamir-scc-util-apply-scale

Similar to apply-offset.py, but operates on data stored in a file. Applies a numeric offset to each data point.

```
usage: clamir-scc-util-apply-scale [-h] [-v VALUE] [-o OFFSET]

options:
  -h, --help           show this help message and exit
  -v, --value VALUE    value
  -o, --offset OFFSET  address offset
```

## clamir-scc-util-apply-scale-file

Scales input values by a multiplier. Could be used for normalization, unit conversion, or adjusting amplitudes.

```
usage: clamir-scc-util-apply-scale-file [-h] [-i INPUT] [-o OFFSET]

options:
  -h, --help           show this help message and exit
  -i, --input INPUT    input file
  -o, --offset OFFSET  address offset
```

## clamir-scc-util-apply-scale

Like apply-scale.py, but reads input from a file and applies the scaling transformation to its contents.

```
usage: clamir-scc-util-apply-scale [-h] [-v VALUE] [-o OFFSET]

options:
  -h, --help           show this help message and exit
  -v, --value VALUE    value
  -o, --offset OFFSET  address offset
```

## clamir-scc-util-generate-correction-table

Like generate uniform sequence, generate correction table script create the nuc in the interchangeable format .nuc
with a header of format

```
[ header : vector<uint8> (constant value : 'NUCD') ][ scale : float32le ( default value: 1.0 ) ][ table : vector<float32, 4096> ( constant value: [] 1.0 ... 1.0 ] )]
```

```
usage: clamir-scc-util-generate-correction-table [-h] [-v VALUE] [-o OUTPUT]

options:
  -h, --help           show this help message and exit
  -v, --value VALUE    value
  -o, --output OUTPUT  output file
```