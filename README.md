# build-python-env
Builds python environment and install requirement according to the requirements/constraints files/parameters

An example use is given as follows:
```
  name: Consume composite action

  on:
    workflow_dispatch:
  
  jobs:
    build:
      runs-on: ubuntu-latest
  
      steps:
        - uses: actions/checkout@v2
        - name: Composite action
          uses: egebeysel/build-python-env@v1
          with:
            python_version: 3.8
            requirements_file: requirements2.txt
            constraints_file: constraints2.txt
            requirements: |
                numpy
                Flask
            constraints: |
                numpy>=1.20
                pandas>=2.0
                python-dateutil==2.8.2
                pytz==2023.3.post1
                six==1.16.0
                tzdata==2023.3
            run: |
              python script.py
              python script.py
```

