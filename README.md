# proximity-system

NVIDIA Jetson 기반 AI 비전 시스템 프로젝트입니다.

## 디렉토리 구조

- **proximity-app/**  
  Rust 기반 이벤트 처리 애플리케이션입니다. DeepStream과 UDS를 통해 통신하며 이벤트를 판단하고 Smart Record를 제어합니다.

- **jetson-bsp/**  
  Jetson BSP 작업 공간입니다. Linux 커널, 디바이스 트리, 카메라 드라이버, DeepStream 애플리케이션, Sysroot, 패치 및 빌드/배포 환경을 포함합니다.

- **protocol/**  
  DeepStream 애플리케이션과 Rust 애플리케이션 간 통신에 사용하는 공통 프로토콜을 정의합니다.

- **dockerfiles/**  
  Rust 크로스 빌드를 위한 Docker 환경을 제공합니다.

## 시스템 구성

```
Camera
   │
   ▼
Jetson BSP
   │
   ├── Camera Driver
   ├── DeepStream
   └── Smart Record
   │
   ▼
proximity-app
   │
   ▼
Event Detection / UDS Control
```

- 현재 카메라 드라이버부터 사용자 공간 애플리케이션까지 전체 시스템을 하나의 프로젝트에서 관리하고 있습니다.