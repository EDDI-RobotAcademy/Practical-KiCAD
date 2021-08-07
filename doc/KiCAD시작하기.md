# Getting Started in KiCAD

## 1. Introduction to KiCAD
### 1.1. Downloading and Installing KiCAD
#### 1.1.1. Under GNU/Linux
#### 1.1.2. Under Apple macOS
#### 1.1.3. Under Windows
### 1.2. Support

## 2. KiCAD Workflow
### 2.1. Overview
### 2.2. Forward and Backward Annotation

## 3. Using KiCAD
### 3.1. Shortcut Keys
#### 3.1.1. Accelerator keys
#### 3.1.2. Hotkeys
#### 3.1.3. Example

## 4. Draw Electronic Schematics
### 4.1. Using Eeshema
### 4.2. Bus Connections in KiCAD

## 5. Layout Printed Circuit Boards
### 5.1. Using Pcnew
### 5.2. Generate Gerber Files
### 5.3. Using GerbView
### 5.4. Automatically route

## 6. Forward Annotation in KiCAD

## 7. Make Schematic Symbols in KiCAD
### 7.1. Using Component Library Editor
### 7.2. Export, Import and Modify Library Components
### 7.3. Make Schematic Components with Quicklib
### 7.4. Make a High Pin Count Schematic Component

## 8. Make Component Footprints
### 8.1. Using Footprint Editor

## 9. Note about Portability of KiCAD Project Files

## 10. More about KiCAD Documentation
### 10.1. KiCAD Documentation on the Web

```make
정교한 전자 인쇄 회로 기판의 성공적인 개발을 위한 KiCAD 마스터에 대한 필수적이고 간결한 안내서입니다.

Copyright

이 문서는 아래 나열된 기고자에 의해 Copyright © 2010-2018 저작권을 가집니다.
GNU General Public License(http://www.gnu.org/licenses/gpl.html), 버전 3이상 또는 Creative Commons Attribution License(http://www.gnu.org/licenses/gpl.html)의 조건에 따라 배포 또는 수정할 수 있습니다.

이 안내서에 있는 모든 상표는 합법적인 소유자의 소유입니다.

Contributors

David Jahshan, Phil Hutchinson, Fabrizio Tappero, Christina Jarron, Melroy van den Berg.

Feedback

버그 보고서, 제안 사항 또는 새 버전을 아래로 보내주세요.
* KiCad 설명서 정보:
  https://gitlab.com/kicad/services/kicad-doc/issues
* KiCad 소프트웨어 정보:
  https://gitlab.com/kicad/code/kicad/issues
* KiCad 소프트웨어 구현(i18n): https://gitlab.com/kicad/code/kicad-i18n/issues

Publication date

2015, May 16.
```make

# Chapter 1

## KiCad 소개

```make
KiCad는 전자회로와 PCB 아트웍을 생성하기 위한 오픈소스 툴이다.

단일 표면 아래에서 KiCad는 다음의 독립실행 툴과 통합한다.

프로그램	설명	확장자
KiCad	프로그램 매니저	*.pro
Eeshema	회로도(schematic)와 컴포넌트(Component) 편집기	*.sch, *.lib, *.net
Pcbnew	회로기판과 footprint 편집기	*.kicad_pcb, *.kicad_mod
GerbView	거버(Gerber)와 드릴링 파일 뷰어	\*.g\*, *.drl, etc
Bitmap2Componet	비트맵 이미지를 컴포넌트 또는 footprints로 변환	*.lib, *.kicad_mod, *.kicad_wks
PCB Calculator	컴포넌트, 트랙 폭(track width), 전기적 공간(electric spacing), 색상코드, ...	None
PI Editor	페이지 레이아웃 편집기	*.kicad_wks
```make

Note  

```make
파일 확장자 목록은 완전하지 않고 단지 KiCad가 지원하는 파일의 부분만을 포함한다. 이것은 어떤 파일이 각 KiCad 응용프로그램에 사용되는지에 대한 기본적인 이해를 하는데 도움이 된다.

KiCad는 복잡한 전자 보드의 성공적인 개발과 유지에 사용되기에 충분히 성숙한 것으로 생각할 수 있다.

KiCad는 어떤 보드크기 제한도 없고 copper 32레이어, technical 14레이어, auxiliary 32레이어까지 다룰 수 있다. KiCad는 프린트 보드 제작, 포토 플로터용 거버파일, 드릴링 파일, 컴포넌트 위치 파일 등을 위해 필요한 모든 파일을 생성할 수 있다.

오픈소스(GPL Licensed)인 KiCad는 오픈소스 기반의 전자 하드웨어 제작을 지향하는 프로젝트에 이상적인 도구입니다.

인터넷에서 KiCad의 홈페이지는 아래와 같습니다:
http://www.kicad-pcb.org/
```

## 1.1. KiCad 다운로드 및 설치

```make
KiCad는 GNU/Linux, Apple macOS 및 Windows에서 실행됩니다.
아래 사이트에서 최신 지침과 다운로드 링크를 찾을 수 있습니다:
http://www.kicad-pcb.org/download/
```

중요!  

```make
KiCad 안정 릴리스는 KiCad 안정 릴리스 정책에 따라 주기적으로 만들어집니다.
새로운 기능이 개발 분기에 지속적으로 추가되고 있습니다.
이러한 새로운 기능을 활용하고 테스트를 통해 도움을 받으려면 플랫폼에 대한 최신 야간 빌드 패키지를 다운로드 하십시오.
Nightly 빌드는 파일 손상, 잘못된 Gerber 생성 등과 같은 버그를 유발할 수 있지만 KiCad 개발 팀의 목표는 새로운 기능 개발 중에 개발 분기를 최대한 사용 가능하게 유지하는 것입니다.
```

### 1.1.1. GNU/Linux에서 설치

```make
안정적인 KiCad 릴리스는 대부분의 배포판 패키지 관리자에서 kicad 및 kicad-doc로 찾을 수 있습니다.
배포판에서 최신 안정 버전을 제공하지 않는 경우 불안정한 빌드에 대한 지침을 따르고 최신 안정 버전을 선택하여 설치하세요.

Ubuntu에서 KiCad의 불안정한 야간 빌드를 설치하는 가장 쉬운 방법은 PPA 및 Aptitude를 사용하는 것입니다.
터미널에 다음을 입력하세요:
```

```make
sudo add-apt-repository --yes ppa:kicad/kicad-5.1-releases
sudo apt-get update
sudo apt-get install --install-recommends kicad
```

### 1.1.2. 애플 맥OS 설치

```make
macOS용 KiCad의 안정적인 빌드는 아래서 찾을 수 있습니다:
http://downloads.kicad-pcb.org/osx/stable/

불안정한 야간 개발 빌드는 아래에서 찾을 수 있습니다:
http://downloads.kicad-pcb.org/osx/stable/
```

### 1.1.3. 윈도우 설치

```make
Windows용 KiCad의 안정적인 빌드는 아래에서 찾을 수 있습니다:
http://downloads.kicad-pcb.org/windows/stable/ 

Windows의 경우 야간 개발 빌드는 아래에서 찾을 수 있습니다:
http://downloads.kicad-pcb.org/windows/stable/
```

## 1.2. Support

```make
아이디어, 의견 또는 질문이 있거나 도움이 필요한 경우 아래를 따르세요:

포럼에 방문하세요:
https://forum.kicad.info/

Freenode에서 #kicad IRC channel에 가입하세요:
https://webchat.freenode.net/?channels=kicad

튜토리얼 보기:
https://www.kicad.org/help/learning-resources/
```

# 2. KiCad Workflow

```make
다른 PCB 설계 소프트웨어와 유사하지만, KiCad는 회로 컴포넌트와 footprint가 분리된 워크플로우가 특징이다.  
회로도가 생성된 이후에만 footprint가 컴포넌트에 할당될 수 있다.  
```

## 2.1. Overview

```make
KiCad 작업흐름(Workflow)은 회로도와 보드 레이아웃 설계 두가지 주요 작업으로 구성된다. 회로도 컴포넌트 라이브러리와 PCB footprint 라이브러리 모두 이 주요 작업에 모두 필요하다. KiCad는 많은 컴포넌트와 footprint를 포함하고 또한 새로 만들기 위한 툴 또한 가지고 있다.

아래 그림에서 KiCad 작업흐름을 볼 수 있다. 흐름도는 작업해야 할 단계와 순서를 설명한다. 해당될 때 편의를 위해 아이콘이 추가되었다.
```

[ 그림 ]

```make
구성 요소 생성에 대한 자세한 내용은 Schematic Symbols 만들기를 참조하세요.
새로운 footprint를 만드는 방법에 대한 자세한 내용은 Component Footprints 만들기를 참조하세요.

Quicklib은 웹 기반 인터페이스로 KiCad 라이브러리 구성 요소를 빠르게 생성할 수 있는 도구입니다.
Quicklib에 대한 자세한 내용은 Quicklib를 사용하여 Schematic Components 만들기를 참조하세요.
http://kicad.rohrbacher.net/quicklib.php
```

## 2.2. Forward and backward annotation

```make
전자 회로도가 완전히 그려지면 다음 단계는 PCB로 전송하는 것입니다.
종종 추가 구성 요소를 추가하거나 부품을 다른 크기로 변경하거나 네트워크 이름을 변경하는 등의 작업이 필요할 수 있습니다.
이는 Forward Annotation 또는 Backward Annotation의 두 가지 방법으로 수행할 수 있습니다.

Forward Annotation은 회로 정보를 일치하는 PCB 레이아웃으로 보내는 절차이다. 이것은 적어도 한번은 초기에 PCB로 회로를 임포트해야 하기 때문에 기본이되는 특성이다.
그 후에 포워드 어노테이션은 늘어난 회로 변화를 PCB에 보낼 수 있게 한다.
좀 더 자세한 내용은 여기를 참조하자.

Backward Annotation은 PCB 레이아웃 변화를 일치하는 회로로 보내는 절차이다.
Backward Annotation에 대한 두가지 일반적인 원인은 게이트 스왑(gate swap)과 핀 스왑(pin swap)이다.
이런 경우에 기능적으로 동일한 게이트 또는 핀이 있지만 정확한 게이트 또는 핀을 선택하는 것에 대한 강한 경우가 있는 레이아웃 중에만 있다.
PCB에서 선택이 이루어지면 이 변화는 회로로 다시 전달된다.
```

# Chapter 3

## Using KiCad

### 3.1. Shortcut keys

