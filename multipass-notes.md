# Ubuntu Multipass on OSX

## Setup

Install with homebrew:
```
brew update
brew upgrade
brew install --cask multipass
```

## Commands:

### List available images:
```
multipass find
```

### Create a vm:
```
multipass launch 20.04 --cpus 2 --disk 8G --mem 2G --name test-server
```

### List vms:
```
multipass list
```

### Show vm info:
```
multipass info test-server
```

### Open a shell on vm:
```
multipass shell test-server
```

### Run a command on vm:
```
multipass exec test-server -- ip a
```

### Stop and start a vm:
```
multipass stop test-server
multipass start test-server
```

### Mount local dir in vm:
```
multipass mount ~/workspace/ test-server:/home/ubuntu/workspace
```

### Unmount dir in vm:
```
multipass umount test-server:/home/ubuntu/workspace
```

### Delete a vm:
```
multipass delete test-server
multipass purge
```
or:
```
multipass delete --purge test-server
```

