pyad1
================

A Python library for parsing AccessData AD1 forensic images (FTK Imager).
This is a work in progress, please use with caution.

### Installation

```bash
git clone https://github.com/pcbje/pyad1
cd pyad1
python setup.py install
```

### Usage

```python
# python demo.py some-image.ad1
import sys

import pyad1.reader

with pyad1.reader.AD1Reader(sys.argv[1]) as ad1:
        for item_type, parent_path, filename, metadata, content in ad1:
            print (parent_path, filename)
            with open(filename, 'wb') as out:
                    out.write(content)
            # ...
```

### Todo

* Format documentation
* Hash verification
* Image creation
* Encrypted images
