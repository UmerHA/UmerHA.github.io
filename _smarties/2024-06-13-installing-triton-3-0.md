---
title: "Installing Triton 3.0.0"
collection: smarties
---

As of June 13 2024, to get Triton 3.0 you have to install it from source, like so:

1. Uninstall your current Triton version
```
pip uninstall triton 
```

2. Clone the Triton repo
```
git clone https://github.com/triton-lang/triton.git
```

3. Install dependencies
```
cd triton
pip install ninja cmake wheel # build-time dependencies
pip install -e python # takes a couple of minutes
```

4. Run setup
```
cd python
python setup.py install
```

Hope I saved you some hassle & time.

\- Umer
