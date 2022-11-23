# Hướng dẫn cài Minikube

## Môi trường cài đặt

* Laptop MSI
* Windows 11 Home Single Language 64-bit
* 12 CPUs (Core Intel i7)
* 24GB RAM
* Virtualbox 6.1

## Cài đặt Minikube

Run PowerShell as administrator. Tải về:

```
New-Item -Path 'c:\' -Name 'minikube' -ItemType Directory -Force
Invoke-WebRequest -OutFile 'c:\minikube\minikube.exe' -Uri 'https://github.com/kubernetes/minikube/releases/latest/download/minikube-windows-amd64.exe' -UseBasicParsing
```

Add to Path

```
$oldPath = [Environment]::GetEnvironmentVariable('Path', [EnvironmentVariableTarget]::Machine)
if ($oldPath.Split(';') -inotcontains 'C:\minikube'){ `
  [Environment]::SetEnvironmentVariable('Path', $('{0};C:\minikube' -f $oldPath), [EnvironmentVariableTarget]::Machine) `
}
```

Kiểm tra minikube đã được cài đặt xong bằng cách tắt PowerShell và mở lại sau đó run lệnh minikube.

### Start Minikube với Virtualbox

Run PowerShell as administrator.

```
minikube start --driver=virtualbox --cpus=8 --memory=16000 --container-runtime=containerd --disk-size=80g
```

Start dashboard:

```
minikube dashboard
```

### Vận hành Minikube

Pause Kubernetes without impacting deployed applications:

`minikube pause`

Unpause a paused instance:

`minikube unpause`

Stop the cluster

`minikube stop`
