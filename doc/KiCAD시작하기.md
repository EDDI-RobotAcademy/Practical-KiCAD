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

```make
KiCad는 관련되지만 다른 엑셀러레이터(accelerator)와 핫키(hotkey) 두가지 단축키가 있다.
두가지 모두 마우스를 이용해 명령을 수행하는 것 대신 키보드로 KiCad에서 작업속도를 높힌다.
```

#### 3.1.1. Accelerator keys

```make
엑셀러레이터 키는 메뉴 또는 쿨바 아이콘을 클릭하는 것과 동일한 동작을 한다.
메뉴 또는 툴바 아이큰을 클릭하는 것은 해당 명령을 입력하지만 클릭된 마우스 버튼을 벗어날 때까지 아무런 동작도 하지 않는다.
엑셀러레이터 키는 명령모드로 들어가고 싶지만 즉각적인 동작을 원하지 않을때 사용한다.

엑셀러레이터 키는 아래 그리과 같이 모든 메뉴의 오른쪽 옆에 나타난다.
```

[ 그림 ]

#### 3.1.2. Hotkeys

```make
핫키는 엘셀러레이터 키와 마우스 왼쪽 클릭을 합친것과 같다.
핫키는 사용하는 것은 현재 커서 위치에서 즉각적으로 명령을 시작한다.
작업흐름에 끼어드는 것 없이 빠르게 명령을 바꾸기 위해 핫키를 사용한다.

KiCad 툴내에서 핫키를 보려면 Help → List Hotkeys 또는 Ctrl + F1 키를 누른다.
```

[ 그림 ]

```make
Preferences → Hotkeys Options 메뉴에서 핫키의 할당을 수정할 수도 임포트 또는 익스포트 할 수 있다.

이 문서에서는 핫키를 대괄호(bracket)으로 표현한다. 예를 들어 [a]는 키도드에서 "a"키를 누르는 것이다.
```

#### 3.1.3. Example

```make
회로도에서 선(wire)를 추가하는 것에 대한 간단한 예를 생각해 보자.

엑셀러레이터 키로는 "Add wire" 명령을 호출하기 위해 "Shift + W"를 누른다.(커서가 바뀐다.)
다음으로 선을 그리기 시작하기 위해 원하는 선의 시작위치에서 왼쪽 마우스를 클릭한다.

핫키로는 간단하게 [W]를 누르면 현제 커서 위치에서 즉시 선이 시작한다.
```

# Chapter 4

## Draw electronic schematics

```make
이 문단에서는 KiCad로 회로도(electronic schematic)을 그리는 방법에 대해 알아본다.
```

### 4.1. Using Eeschema

```make
1. 리눅스에서 터미널에 'kicad'를 입력한다.
그러면 KiCad 프로젝트 매니저의 메인 윈도우에 있게 된다.
여기서 Eeschema, Schematic Library Editor, Pcbnew, PCB Footprint Editor, GerbView, Bitmap2Component, PCB Calculator, PI Editor 8가지 독립 실행 소프트웨어 툴에 접근할 수 있다.
```

[ 그림 ]

```make
2. File → New → Project로 새로운 프로젝트 'Name'을 생성한다. 프로젝트 파일은 자동으로 ".pro" 확장자를 갖는다. 정확한 다이얼로그의 모습은 사용하는 플랫폼에 따라 다르지만 새로운 디렉토리를 생성하는 체크박스가 있다. 작업할 디렉토리가 이미 있지 않다면 체크박스에 체크한다. 모든 프로젝트 파일이 이 디렉토리에 저장된다.
```

3. 전자회로를 그려보자.  
[ 그림 ] 아이콘을 선택하여 Eeschema 회로 편집기(shematic editor)를 시작한다.  
이 아이콘은 왼쪽에서 첫번째 버튼이다.  

```make
4. 툴바에서 'Page setting'아이콘 [ 그림 ]을 누른다. 적절한 'paper size'를 설정하고 제목(Title)을 'Tutorial1'으로 입력한다. 
여기서 필요하다면 더 많은 정보를 입력할 수 있다. 'OK'를 누르면 이 정보가 도면의 오른쪽 아래에 보인다. 
확대/축소를 위해서는 마우스 휠을 사용하고 전체 회로를 저장하는 것은 File → Save를 사용한다.
```

이제 첫번째 컴포넌트를 위치시켜 보자. 오른쪽 툴바에서 'Place Symbol'아이콘 [ 그림 ]을 누른다.  
핫키로 [a] - 'Add Symbol'을 사용할 수도 있다.  

```make
6. 회로도의 중간을 클릭하면 Choose Symbol Window가 화면에 나타난다. 
첫번째 컴포넌트로는 저항(resistor)을 사용한다. 
Resistor의 'R'로 검색(search)/필터링(filter)한다. 
저항위에 'Device' 헤더가 있는 것을 알 수 있다. 
'Device' 헤더는 컴포넌트가 위히한 라이브러리의 이름으로 'Device'는 상당히 포괄적이면서 유용한 라이브러리이다.
```

[ 그림 ]

```make
7. 저항을 더블클릭하면 'Choose Symbol'윈도우가 닫힌다.
원하는 곳에서 클릭하여 회로도에 컴포넌트를 위치시킨다.

8. 컴포넌트에서 확대하기 위해 돋보기 아이콘을 클릭한다.
아니면 확대/축소를 하기 위해 마우스 휠을 사용한다.
수직과 수평으로 이동하기 위해 마우스 휠 버튼을 누른다.

9. 컴포넌트 'R' 위에 마우스를 올려놓고 [r]을 누르면 컴포넌트가 회전한다.
컴포넌트를 회전시키기 위해 컴포넌트를 실제로 클릭할 필요가 없다.

때때로 마우스가 다른것위에 있다면, 메뉴가 나타날 것이다.
자주 KiCad에서 Clarify Selection menu를 볼 것이다.
이것은 서로 꼭대기에 있는 객체에서 작업할 수 있도록 한다.
이런 경우,만약 메뉴가 나타나면 'Symbol...R...'에서 동작을 KiCad가 수행하하도록 한다.

10. 컴포넌트의 중앙에서 오른쪽 클릭을 하고 Properties &rarr Edit Value를 선책한다.
마우스를 컴포넌트 위에 놓고 [v]를 누르는 것도 동일하다.
대신 [e]는 좀더 포괄적인 속성 윈도우를 보여줄 것이다.
아래 오른쪽 클릭 메뉴가 어떻게 가능한 동작에 대한 핫키를 보여주고 있는지 보자.
```

[ 그림 ]

```make
11. Edit Value 필드가 나타난다.
현재 값 'R'을 '1k'로 바꾸고 'OK'를 누른다.

참조 필드(Reference Field, R?)은 변경하면 안된다. 이 필드는 이후에 자동적으로 완성된다.
위 저항의 값은 이제 '1K'가 된다.
```

[ 그림 ]

```make
12. 다른 저항을 위치시키기 위해서는 간단하게 저항이 나타나기 원하는 곳을 클릭하면 'Symbol Selection Window'가 다시 나타난다.

13. 이전에 선택한 저항이 'R'로 보이는 이력목록(history list)이 있다.
'OK'를 누르고 컴포넌트를 위치시킨다.
```

[ 그림 ]

```make
14. 실수를 해서 컴포넌트를 지우고 싶은 경우, 해당 컴포넌트를 오픈쪽 클릭하고 'Delete'를 클릭하면 회로도에서 컴포넌트를 제거한다.
다른 방법으로 지우길 원하는 컴포넌트 위에 마우스를 올리고 [delete]를 누를 수도 있다.

15. 또한 이미 회도도에 있는 컴포넌트에 마우스를 올리고 [C]를 눌러 복제할 수도 있다.
원하는 곳을 클릭하여 복제된 컴포넌트를 위치시킨다.

16. 두번째 저항에서 오른쪽 클릭하고 'Drag'를 선택한다.
컴포넌트의 위치를 바꾸고 고정하기 위해 왼쪽 클릭을 한다.
동일한 기능을 컴포넌트 위에 마우스를 위치하고 [g]를 누른다.
[r]은 컴포넌트를 회전시키지만, [x]와 [y]는 x축 또는 y축에 대해 뒤집는다.

Right-Click → Move 또는 [m]은 또한 어떤것이든 움직이기 위한 유용한 옵션이지만, 컴포넌트 레이블 또는 아직 연결되지 않은 컴포넌트에만 사용하는 것이 더 좋다.
해당 경우에 왜 그런지는 이후에 살펴 볼 것이다.

17. 두번째 저항에 마우스를 올리고 [v]를 눌러 'R'을 '100'으로 수정한다.
'Ctrl + Z'로 수정한 작업을 되돌릴 수 있다.

18. 그리드 크기(grid size)를 바꾼다.
아마 회로도의 모든 컴포넌트가 커다란 간격의 그리드를 따라 움직일 것이다.
Rignt-Click → Grid로 그리드의 크기를 쉽게 바꿀 수 있다.
회로도에는 50.0mils의 크리드를 사용하는 것이 권장된다.

19. 이번에는 기본적으로 프로젝트에서 설정되지 않은 라이브러리에서 컴포넌트를 추가한다.
메뉴에서 Preferences → Manage Symbol Libraries를 선택한다.
Symbol Libraries 윈도우에서 Global Library와 Project Specific Libraries인 두갱의 탭을 볼 수 있다.
각각은 sym-lib_table 파일 하나를 갖는다.
라이브러리(.lib 파일)이 사용가능하려면 이 sym-lib-table 파일주 어느 하나에 있어야 한다.
만약 로컬시스템에 라이브러리 파일이 있고 아직 사용할 수 없다면, sym-lib-table 파일중 하나에 추가할 수 있다.
여기서는 이미 사용가능한 라이브러리를 추가해 볼 것이다.

20. Project Specific table을 선택한다. 테이블 아래 파일 browser를 클릭한다.
로컬 PC에 설치된 공식 KiCad 라이브러리 위치를 찾는다.
수백개의 .dcm과 .lib파일을 포함하는 library 디렉토리를 찾는다.
윈도우에서는 C:\Program Files (x86)\KiCad\Share\를 리눅스에서는 /usr/share/kicad/library/를 한번 찾아보자.
디렉토리를 찾아 선택하고 'MCU_Microchip_PIC12.lib' 라이브러리는 추가한 후 윈도우를 닫는다.
이 라이브러리는 목록의 맨 마지막에 추가될 것이다.
이제 이것의 닉네임을 선택하여 'microchip_pic12mcu'로 바꾸고 'OK'로 Symbol Libraries 윈도우를 닫는다.

21. 컴포넌트를 회로에 추가하는 단계를 반복한다.
이번에는 'Device'라이브러리 대신 'microchip_pic12mcu'에서 'PIC12C508A-ISN' 컴포넌트를 선택한다.

22. 마이크로컨트롤러 컴포넌트 위에 마우스를 위치시킨다.
G0과 G1 핀이 오른쪽을 가르키도록 [y]를 눌러 Y축 기준으로 반전시킨다.

23. 컴포넌트를 회로에 추가하는 단계를 반복한다.
이번에는 'Device' 라이브러리에서 'LED'를 선택한다.

24. 아래처럼 모든 컴포넌트를 배치한다.
```

[ 그림 ]

```make
25. 이번에는 3핀 컨넥터를 위한 'MYCONN3' 회로 컴포넌트를 만들어야 한다.
어떻게 설계부터 컴포넌트를 만드는지를 배우기 위해 Make Schematic Symbos in KiCad 순서로 건너 뛴 후 다시 돌아올 수도 있다.

26. 이제 새롭게 만든 컴포넌트를 추가할 수 있다.
[a]를 누르고 'myLib' 라이브러리에서 'MYCONN3' 컴포넌트를 선택한다.

27. 컴포넌트 식별자 'J?'가 'MYCONN3' 레이블 아래에 나타난다.
만약 이 위치를 바꾸고 싶다면, 'J?'를 오른쪽 클릭하고 'Move Field' ([m]과 동일)을 선택한다.
'J?'를 아래 그림과 같이 위치시킨다.
'MYCONN3' 레이블 또한 원하는 만큼 옮길 수 있다.
```

[ 그림 ]
