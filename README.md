# Batch Job Generator

A general-purpose batch job generator designed for HPC environments. 

User provides:
- a master job template (.js, .mjs)
- any input list/matrix filepath required for job specifications
- a config file with all the above information documented

The scripts runs on the system input of config filename. The config should be formatted as `key=values` pairs per row. A `key` accepts any naming at the discretion of users, but should be consistent with the placeholder naming in the master job template. 
A'value' accepts three types of input: filepath, filepath with columns specified, python-style patterns with `{keys/placeholders}`. 
In general, the config specifies the input/output filepaths, job directories, and job settings, and the script will resolve all the placeholders, expands the rows of the config input, and generate the jobs according to the input data length, and specify the job setting and job dependence in a separate submission file, ready to be submitted the HPC system. 

In short:

`Config in->Master template, Lists/Matrices->Batch jobs out`

No workflow assumptions. No fixed naming rules. Flexible for generic job generation in any HPC system. 

## Key features

### Config format

