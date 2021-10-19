# chaos_brain


* requirements:

```
conda create -n chaos_brain python=3.6
conda install protobuf -n chaos_brain
```

## deploy with source

* `run.sh`

```
#!/bin/bash
source activate chaos_brain
nohup python3 main.py 8801 > log_port_8801.log 2>&1 &
```

## deploy with bin

* `pyinstaller`

```
conda install protobuf -n chaos_brain
```

* `publish.sh`

```
#!/bin/bash
rm -f *.spec
rm -rf ./dist
rm -rf ./build
source activate chaos_brain
pyinstaller -F main.py

# bin: main
# path: ./dist/main
```

* `run.sh`

```
#!/bin/bash
if [ ! -d "log" ]; then
        mkdir log
fi
nohup ./main 8801 > console.log 2>&1 &
```

## start service

```
cd /path/to/chaos_brain
sh run.sh
```
