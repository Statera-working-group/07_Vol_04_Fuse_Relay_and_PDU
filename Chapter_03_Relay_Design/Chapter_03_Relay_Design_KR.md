**Volume 04. Fuse, Relay, and Power Distribution Unit**

# Chapter 03. Relay Design

## 03.01. Electromechanical Relay Basics

![](images/image1.png){width="7.268055555555556in" height="7.268055555555556in"}

전자기계식 릴레이(Electromechanical Relay)는 전자기 메커니즘(Electromagnetic Mechanism)을 이용하여 하나 이상의 전기 접점(Electrical Contact)을 열거나 닫는 전기 제어식 스위칭 장치(Electrically Controlled Switching Device)이다. 비교적 낮은 전력의 제어 신호(Control Signal)를 이용하여 서로 다른 전압이나 전류에서 동작하는 별도의 부하 회로(Load Circuit)를 스위칭할 수 있다. 이러한 제어 측(Control Side)과 스위칭 측(Switched Side)의 분리는 릴레이를 전력 분배(Power Distribution), 신호 절연(Signal Isolation), 인터록(Interlocking), 액추에이터 제어(Actuator Control)에 유용하게 만든다.

기본적인 릴레이는 코일(Coil), 자기 코어(Magnetic Core), 아마추어(Armature), 복귀 스프링(Return Spring), 고정 접점(Stationary Contact), 가동 접점(Movable Contact), 단자(Terminal), 절연 외함(Insulating Enclosure)으로 구성된다. 코일 양단에 전압이 인가되면 권선(Winding)을 흐르는 전류가 코어에 자속(Magnetic Flux)을 발생시킨다. 이에 따라 발생한 전자기력(Electromagnetic Force)이 가동 아마추어를 코어 방향으로 끌어당기며, 아마추어의 기계적 움직임에 의해 연결된 접점 상태가 변하고 결과적으로 부하 회로의 전기적 연결 상태가 변경된다.

코일의 전원이 차단되면 자기장(Magnetic Field)이 소멸하고 복귀 스프링이 일반적으로 아마추어를 원래의 정지 위치(Rest Position)로 이동시킨다. 이에 따라 여자 상태(Energized State)와 비여자 상태(De-energized State)라는 두 가지 기본 동작 상태가 형성된다. 이러한 상태와 관련된 접점은 일반적으로 상시 개방(Normally Open, NO)과 상시 폐쇄(Normally Closed, NC)로 구분한다. 상시 개방 접점은 릴레이가 작동한 후 도통하며, 상시 폐쇄 접점은 릴레이가 비활성 상태일 때 도통하고 릴레이가 여자되면 개방된다.

릴레이의 접점 구성(Contact Arrangement)은 일반적으로 극(Pole)과 투(Throw)라는 용어를 사용하여 표현한다. 단극 단투(Single-Pole Single-Throw, SPST) 릴레이는 하나의 전기 경로를 제어하고, 단극 쌍투(Single-Pole Double-Throw, SPDT) 릴레이는 하나의 공통 단자(Common Terminal)를 두 개의 대체 경로 사이에서 전환한다. 릴레이는 여러 개의 극을 포함할 수도 있으며, 이를 통해 하나의 코일로 여러 회로를 동시에 스위칭할 수 있다. 이러한 기계적 연동(Mechanical Linkage)은 하나의 제어 명령으로 동기화된 스위칭이나 전기적 인터록(Electrical Interlocking)을 구현해야 할 때 유용하다.

코일은 정격 전압(Nominal Voltage), 코일 저항(Coil Resistance), 소비 전력(Power Consumption), 동작 전압(Pickup Voltage), 복귀 전압(Dropout Voltage) 등의 파라미터로 특성이 정의된다. 정격 전압을 인가하면 신뢰성 있는 동작에 필요한 전자기력을 생성할 수 있을 정도의 코일 전류가 형성된다. 실제 동작 전압은 일반적으로 정격 전압보다 낮으며, 복귀 전압은 이보다 더욱 낮다. 이러한 차이는 히스테리시스(Hysteresis)를 형성하여 제어 전압이 동작 임계값 부근에서 변동할 때 불안정한 스위칭이 발생하는 것을 방지하는 데 도움을 준다.

직류 릴레이 코일(DC Relay Coil)의 정상 상태 전류(Steady-State Current)는 옴의 법칙(Ohm\'s Law)에 따라 I = V/R로 근사할 수 있으며, 여기서 V는 인가된 코일 전압이고 R은 권선 저항이다. 따라서 코일 전력은 P = VI 또는 P = V²/R로 계산할 수 있다. 이러한 관계는 단순하지만 코일 저항은 온도에 따라 변한다. 권선 온도가 상승하면 저항이 증가하고 전류가 감소하며 사용 가능한 전자기력이 감소할 수 있으므로, 릴레이 구동 설계(Relay Drive Design)에서는 온도를 중요한 요소로 고려해야 한다.

릴레이의 접점 측(Contact Side)은 코일 측(Coil Side)과 독립적으로 선정해야 한다. 접점 정격(Contact Rating)은 안전하게 스위칭할 수 있는 전압, 전류 및 부하 유형을 규정한다. 특정 저항성 전류(Resistive Current)에 대해 정격이 정의된 릴레이가 모터(Motor), 솔레노이드(Solenoid), 변압기(Transformer), 용량성 부하(Capacitive Load) 또는 기타 리액티브 장치(Reactive Device)에 대해서도 동일한 전류를 지원한다고 볼 수는 없다. 부하 특성은 스위칭 스트레스(Switching Stress)를 결정하며, 유도성 및 용량성 회로에서는 정상 상태 값보다 훨씬 큰 과도 전류(Transient Current)나 과도 전압(Transient Voltage)이 발생할 수 있다.

릴레이 접점이 닫힐 때 일반적으로 즉시 완벽하게 안정된 전기적 연결이 형성되는 것은 아니다. 기계적 탄성(Mechanical Elasticity)으로 인해 접점 바운스(Contact Bounce)가 발생하며, 접점이 안정되기 전 짧은 시간 동안 반복적으로 접촉과 분리를 수행할 수 있다. 접점 바운스는 디지털 회로(Digital Circuit)에서 전기적 노이즈(Electrical Noise)와 여러 번의 상태 전환을 발생시키고, 전력 회로(Power Circuit)에서는 국부적인 아크(Arc)를 발생시킬 수 있다. 그 영향은 부하와 응용 분야에 따라 달라지지만, 릴레이가 전자 제어기(Electronic Controller) 또는 민감한 모니터링 회로(Monitoring Circuit)와 연결될 때 반드시 고려해야 한다.

유도성 부하(Inductive Load)를 개방하는 것은 또 다른 중요한 과제를 발생시킨다. 인덕턴스(Inductance)를 흐르는 전류는 순간적으로 변할 수 없기 때문에 전류 경로가 차단되면 높은 과도 전압이 발생할 수 있다. 이러한 전압은 분리되는 릴레이 접점 사이에서 아크를 발생시켜 접점 침식(Contact Erosion)을 가속하고 전자기 간섭(Electromagnetic Interference, EMI)을 발생시킬 수 있다. 따라서 부하 특성과 요구되는 복귀 동작에 따라 플라이백 다이오드(Flyback Diode), 과도 전압 억제기(Transient Voltage Suppressor, TVS), RC 스너버(RC Snubber) 또는 기타 억제 네트워크(Suppression Network)를 적용한다.

릴레이 코일 자체도 유도성 부품(Inductive Component)이다. 직류 코일이 차단되면 저장되어 있던 자기 에너지(Magnetic Energy)가 역방향 과도 전압(Reverse-Voltage Transient)을 발생시키며, 이는 릴레이를 구동하는 트랜지스터(Transistor), MOSFET, 집적 드라이버(Integrated Driver) 또는 제어기(Controller)를 손상시킬 수 있다. 따라서 일반적으로 코일 회로의 양단이나 주변에 억제 소자(Suppression Device)를 배치한다. 단순한 플라이백 다이오드는 효과적인 보호 기능을 제공하지만 자기장의 소멸을 늦추므로 릴레이의 기계적 복귀 시간(Mechanical Release Time)을 증가시킬 수 있다.

전기적 절연(Electrical Isolation)은 전자기계식 릴레이의 주요 장점 중 하나이다. 코일과 접점은 직접적인 도전 경로(Conductive Path)가 아니라 자기적·기계적으로 결합되기 때문에 제어 회로를 스위칭 회로로부터 갈바닉 절연(Galvanic Isolation)할 수 있다. 이를 통해 저전압 전자 회로가 고전력 부하를 제어하면서 서로 다른 전기 영역 간의 직접적인 상호작용을 줄일 수 있다. 실제 절연 성능은 내부 이격 거리(Spacing), 절연 재료(Insulation Material), 구조 및 적용 가능한 전압 정격(Voltage Rating)에 따라 결정된다.

접점 저항(Contact Resistance)도 중요한 성능 파라미터이다. 닫힌 릴레이 접점에는 접점 재료(Contact Material), 접촉력(Contact Force), 표면 상태(Surface Condition), 오염(Contamination), 노화(Aging)에 따라 결정되는 작지만 유한한 저항이 존재한다. 높은 전류에서는 작은 저항도 P = I²R에 따른 전력 손실을 발생시킨다. 따라서 과도한 접점 저항은 국부적인 발열(Local Heating), 전압 강하(Voltage Drop), 점진적인 접점 열화(Contact Degradation)를 발생시킬 수 있으며, 적절한 릴레이 선정에서는 스위칭 순간의 과도 조건뿐 아니라 연속 전류도 고려해야 한다.

접점 재료(Contact Material)는 전기 전도도(Conductivity), 용착 저항성(Resistance to Welding), 아크 침식(Arc Erosion), 산화(Oxidation), 예상 스위칭 수명(Expected Switching Life) 사이의 균형을 고려하여 선정한다. 저레벨 신호 접점(Low-Level Signal Contact)은 모터 전력 접점(Motor Power Contact)과 매우 다른 조건에서 동작하기 때문에 응용 분야마다 요구사항도 달라진다. 매우 작은 전류에서는 오염된 표면막을 관통하기 위한 전기 에너지가 부족할 수 있으며, 높은 전류에서는 심각한 아크나 접점 용착(Contact Welding)이 발생할 수 있다. 따라서 접점 정격은 실제 부하 프로파일(Load Profile)을 기준으로 해석해야 한다.

릴레이 수명(Relay Life)은 일반적으로 기계적 수명(Mechanical Life)과 전기적 수명(Electrical Life)으로 구분한다. 기계적 수명은 큰 전기 부하 없이 수행할 수 있는 동작 횟수를 의미하며 주로 아마추어, 스프링, 베어링(Bearing), 기계 구조에 의해 결정된다. 전기적 수명은 스위칭 전류에 의해 접점이 마모되므로 일반적으로 훨씬 짧다. 부하 전류, 전압, 스위칭 주파수(Switching Frequency), 역률(Power Factor), 돌입 전류(Inrush Current), 주변 온도(Ambient Temperature), 억제 전략(Suppression Strategy)은 실제 사용 수명에 큰 영향을 미칠 수 있다.

스위칭 속도(Switching Speed)는 전자기적 및 기계적 동특성(Dynamics)에 의해 제한된다. 코일이 여자된 후 전류가 상승하고 자기력이 형성되며 아마추어가 이동하고 접점이 안정되기까지 일정한 시간이 필요하다. 복귀 과정에서도 유사한 지연이 발생한다. 따라서 전자기계식 릴레이는 반도체 스위치(Semiconductor Switch)보다 훨씬 느리지만, 마이크로초(Microsecond)가 아닌 밀리초(Millisecond) 수준으로 동작하는 많은 전력 제어 기능에는 충분한 스위칭 속도를 제공한다.

릴레이는 코일이 여자 상태를 유지하는 동안에도 전력을 소비한다. 배터리 구동 로봇(Battery-Powered Robot), 모바일 플랫폼(Mobile Platform), 자율이동로봇(Autonomous Mobile Robot, AMR)에서는 여러 릴레이가 장시간 동작할 경우 지속적인 코일 소비 전력이 중요한 요소가 될 수 있다. 상태 유지를 위해 지속적인 코일 전력이 필요하지 않은 경우 래칭 릴레이(Latching Relay)를 사용할 수 있다. 래칭 릴레이는 여자 펄스(Excitation Pulse)가 제거된 후에도 명령된 기계적 위치를 유지하지만, 제어 전략과 고장 상태 동작(Failure-State Behavior)은 일반적인 단안정 릴레이(Monostable Relay)와 다르다.

로봇 전력 아키텍처(Robotics Power Architecture)에서 전자기계식 릴레이는 보조 부하(Auxiliary Load), 조명(Lighting), 펌프(Pump), 팬(Fan), 히터(Heater), 센서(Sensor), 통신 장비(Communication Equipment) 및 기타 서브시스템(Subsystem)의 제어된 전원 연결에 사용할 수 있다. 또한 활성화 체인(Enable Chain)과 전원 시퀀싱(Power Sequencing)에 참여할 수 있다. 높은 전류의 추진 배터리(Propulsion Battery)와 고전압 시스템(High-Voltage System)에서는 일반 릴레이보다 적절한 정격의 컨택터(Contactor)가 사용되므로, 릴레이와 컨택터의 선정은 전압, 전류, 고장 에너지(Fault Energy), 절연 및 안전 요구사항에 따라 결정해야 한다.

릴레이를 이상적인 이진 스위치(Ideal Binary Switch)로 취급해서는 안 된다. 실제 공학적 동작에는 코일 발열(Coil Heating), 동작 및 복귀 임계값(Pickup and Dropout Threshold), 접점 바운스, 스위칭 아크(Switching Arc), 과도 전압, 접점 저항, 기계적 지연(Mechanical Delay), 유한한 동작 수명이 포함된다. 이러한 특성은 배선(Wiring), 퓨즈(Fuse), 전자 드라이버(Electronic Driver), 부하 및 전력 분배 아키텍처와 상호작용한다. 따라서 신뢰성 있는 구현을 위해서는 제어 회로와 스위칭 전력 회로를 함께 고려해야 한다.

실제 설계에서는 정상 동작(Normal Operation), 기동(Startup), 종료(Shutdown), 과부하(Overload), 고장(Fault) 조건에서 릴레이를 평가해야 한다. 코일 전압은 허용 범위 내에서 유지되어야 하고, 접점은 연속 및 과도 부하 전류를 견딜 수 있어야 하며, 억제 회로는 허용할 수 없는 복귀 지연을 발생시키지 않으면서 유도성 에너지를 제어해야 한다. 특히 모바일 로봇 장비(Mobile Robotic Equipment)에서는 진동(Vibration), 충격(Shock), 습도(Humidity), 오염 및 온도와 같은 환경 요소가 중요하다.

전자기계식 릴레이는 솔리드 스테이트 스위칭(Solid-State Switching)의 사용이 증가하고 있음에도 불구하고 직관적인 스위칭 동작, 우수한 갈바닉 절연, 낮은 폐접점 전압 강하(Closed-Contact Voltage Drop), 그리고 적절한 접점 정격을 적용할 경우 교류(AC) 또는 직류(DC) 회로를 모두 스위칭할 수 있다는 장점 때문에 여전히 중요한 가치를 가진다. 반면 기계적 마모(Mechanical Wear), 동작 소음(Acoustic Noise), 제한된 스위칭 속도, 접점 바운스, 반복적인 고에너지 스위칭에 대한 민감성은 주요 한계이다. 이러한 기본 원리를 이해하는 것은 이후 솔리드 스테이트 릴레이(Solid-State Relay, SSR), 코일 구동 회로(Coil Drive Circuit), 접점 보호(Contact Protection), 릴레이 수명 공학(Relay Lifetime Engineering)을 학습하기 위한 기반이 된다.

## 03.02. Solid-State Relay (SSR)

![](images/image2.png){width="7.268055555555556in" height="7.268055555555556in"}

솔리드 스테이트 릴레이(Solid-State Relay, SSR)는 기계적으로 움직이는 접점(Mechanically Moving Contact)을 사용하지 않으면서 전자기계식 릴레이(Electromechanical Relay)와 유사한 제어 기능을 수행하는 전자식 스위칭 장치(Electronic Switching Device)이다. 저전력 입력 신호(Low-Power Input Signal)가 반도체 스위칭단(Semiconductor Switching Stage)을 제어하여 전기 부하(Electrical Load)를 연결하거나 차단한다. 전자적으로 스위칭하기 때문에 SSR은 무소음 동작(Silent Operation), 빠른 응답(Rapid Response), 높은 스위칭 사이클 능력(High Switching-Cycle Capability), 기계적 마모(Mechanical Wear)에 대한 내성을 제공한다.

SSR은 일반적으로 입력 회로(Input Circuit), 절연단(Isolation Stage), 구동 또는 제어 회로(Drive or Control Circuit), 출력 스위칭단(Output Switching Stage)으로 구분된다. 입력부는 마이크로컨트롤러(Microcontroller), PLC, ECU 또는 기타 제어 장치(Control Device)에서 제어 전압이나 전류를 입력받는다. 절연단은 직접적인 도전 연결(Conductive Connection)을 형성하지 않고 명령을 전달하며, 출력 반도체(Output Semiconductor)가 부하를 통과하는 실제 전류의 스위칭을 수행한다.

입력과 출력 사이의 갈바닉 절연(Galvanic Isolation)은 일반적으로 옵토커플러(Optocoupler) 또는 다른 절연 신호 전달 메커니즘(Isolated Signal-Transfer Mechanism)을 사용하여 구현한다. 광절연 SSR(Optically Isolated SSR)에서는 입력 신호가 내부 발광 소자(Light-Emitting Device)를 활성화하고, 방출된 빛이 감광 수신 회로(Photosensitive Receiving Circuit)를 작동시킨다. 이러한 구조를 통해 저전압 제어 전자회로가 고전압 부하를 제어하면서 두 전기 영역 사이의 직접적인 전기적 상호작용을 제한할 수 있다.

출력단(Output Stage)에 사용되는 반도체는 SSR이 교류(AC)용인지 직류(DC)용인지에 따라 크게 달라진다. 교류 SSR(AC SSR)은 일반적으로 트라이액(Triac) 또는 한 쌍의 실리콘 제어 정류기(Silicon-Controlled Rectifier, SCR)를 사용하고, 직류 SSR(DC SSR)은 일반적으로 MOSFET 또는 이와 관련된 트랜지스터 구조(Transistor Structure)를 사용한다. 이러한 소자는 도통 및 턴오프 특성(Conduction and Turn-Off Characteristics)이 서로 다르므로 교류 스위칭용 SSR을 직류 응용 분야에서도 정상적으로 사용할 수 있다고 가정해서는 안 된다.

트라이액 기반 교류 SSR(Triac-Based AC SSR)은 트리거된 후 양방향으로 전류를 도통할 수 있으므로 교류 부하에 적합하다. 일반적으로 부하 전류가 유지 전류(Holding Current) 이하로 감소하면 소자가 턴오프되며, 이는 교류 전류의 영점 교차(Current Zero Crossing) 부근에서 자연스럽게 발생한다. 이러한 특성으로 트라이액은 히터(Heater), 램프(Lamp), 솔레노이드(Solenoid) 및 기타 교류 부하에 실용적이지만, 유도성 부하(Inductive Load)에서는 전압과 전류의 위상이 일치하지 않을 수 있으므로 추가적인 고려가 필요하다.

직류 SSR은 전력 MOSFET(Power MOSFET)을 일반적으로 사용하는데, MOSFET은 전류의 영점 교차와 관계없이 능동적으로 턴온 및 턴오프할 수 있기 때문이다. 직류 또는 혼합 극성 회로(Mixed-Polarity Circuit)에서 양방향 차단(Bidirectional Blocking)이 필요한 경우 두 개의 MOSFET을 백투백 구성(Back-to-Back Configuration)으로 연결할 수 있다. MOSFET 기반 SSR은 배터리 구동 시스템(Battery-Powered System), 로봇공학(Robotics), 산업용 직류 전력 분배(Industrial DC Distribution), 전자식 부하 제어(Electronic Load Control)에서 유용하다.

SSR의 중요한 특성 중 하나는 출력 반도체의 전압 강하(Voltage Drop) 또는 온상태 저항(On-State Resistance)이다. 매우 낮은 폐접점 저항(Closed-Contact Resistance)을 가질 수 있는 전자기계식 릴레이 접점과 달리 반도체 스위치는 전류가 흐르는 동안 도통 손실(Conduction Loss)을 발생시킨다. MOSFET 출력에서는 도통 손실을 P = I²RDS(on)으로 근사할 수 있으며, 다른 반도체 구조에서는 주로 온상태 전압 강하(On-State Voltage Drop)를 기준으로 특성을 나타낼 수 있다.

이렇게 발생한 전력 손실(Power Loss)은 열로 변환되므로 SSR에서 적절하게 방출해야 한다. 따라서 열 설계(Thermal Design)는 특히 높은 연속 부하 전류(Continuous Load Current)를 사용하는 경우 SSR 선정의 핵심 요소가 된다. 데이터시트(Datasheet)의 전류 정격은 특정 방열판(Heat Sink), 주변 온도(Ambient Temperature), 장착 방법(Mounting Method), 공기 흐름(Airflow)을 가정할 수 있다. 전기적으로 충분해 보이는 SSR도 반도체 접합부(Semiconductor Junction)에서 주변 환경으로 이어지는 열저항(Thermal Resistance)을 적절하게 관리하지 않으면 과열될 수 있다.

열저항(Thermal Resistance)은 반도체 접합부에서 패키지(Package), 인터페이스 재료(Interface Material), 방열판, 주변 공기까지 열이 전달될 때 온도가 얼마나 상승하는지를 나타낸다. 접합부 온도(Junction Temperature)는 전력 손실과 해당 열저항 경로를 조합하여 추정할 수 있다. 과도한 온도는 반도체 열화(Semiconductor Degradation)를 가속하고 궁극적으로 영구적인 고장을 발생시킬 수 있으므로 접합부 온도를 제조업체가 허용하는 한계 이하로 유지하는 것이 필수적이다.

전자기계식 릴레이와 다른 또 하나의 중요한 특성은 오프상태 누설 전류(Off-State Leakage Current)이다. 기계식 접점은 개방되었을 때 물리적인 공극(Physical Air Gap)을 형성하지만, 반도체 소자는 일반적으로 OFF 명령 상태에서도 소량의 전류가 흐를 수 있다. 이러한 누설 전류는 큰 부하에서는 중요하지 않을 수 있지만 민감한 회로, LED 램프, 고임피던스 입력(High-Impedance Input), 진단 회로(Diagnostic Circuit), 완전히 차단된 것으로 가정하는 장비에서는 예상하지 못한 동작을 발생시킬 수 있다.

따라서 SSR의 출력을 물리적 절연 스위치(Physical Isolation Switch)와 자동적으로 동일한 것으로 간주해서는 안 된다. 제어 입력과 출력 사이에 갈바닉 절연이 제공되더라도 반도체 출력에는 여전히 누설 전류, 기생 커패시턴스(Parasitic Capacitance), 제한된 차단 능력(Blocking Capability)이 존재할 수 있다. 유지보수 절연(Maintenance Isolation), 비상 차단(Emergency Disconnection), 안전 요구사항에서 가시적이거나 물리적으로 분리된 전류 경로가 요구되는 경우에는 여전히 전자기계식 장치 또는 컨택터(Contactor)가 필요할 수 있다.

교류 SSR은 영점 교차 스위칭(Zero-Cross Switching) 기능을 제공하는 경우가 많다. 영점 교차 SSR(Zero-Cross SSR)은 출력부를 턴온하기 전에 교류 파형(AC Waveform)의 전압이 영점에 가까워질 때까지 기다린다. 이 지점 부근에서 스위칭하면 많은 저항성 부하(Resistive Load)에서 전자기 간섭(Electromagnetic Interference, EMI), 과도 전류(Current Transient), 전기적 스트레스(Electrical Stress)를 감소시킬 수 있다. 이 방법은 임의의 위상각에서 정밀하게 스위칭할 필요가 없는 히터와 유사 부하의 반복적인 제어에 특히 유용하다.

랜덤 턴온 SSR(Random-Turn-On SSR)은 순간 스위칭 SSR(Instantaneous Switching SSR)이라고도 하며, 의도적으로 영점 교차를 기다리지 않고 출력을 활성화한다. 제어 명령에 가깝게 스위칭 타이밍을 맞춰야 하거나 위상각 제어(Phase-Angle Control)가 필요한 경우 유용하다. 그러나 교류 파형의 임의 지점에서 스위칭하면 특히 용량성 부하, 변압기(Transformer), 또는 큰 돌입 특성(Inrush Characteristics)을 가진 부하에서 더 큰 과도 스트레스(Transient Stress)가 발생할 수 있다.

SSR은 아마추어나 접점 메커니즘이 물리적으로 이동할 필요가 없기 때문에 일반적인 전자기계식 릴레이보다 훨씬 빠른 스위칭이 가능하다. 또한 기계적인 접점 바운스(Contact Bounce)가 없어 깨끗한 전자적 상태 전환과 일반 릴레이보다 높은 스위칭 주파수(Switching Frequency)를 구현할 수 있다. 그러나 실제 스위칭 주파수는 반도체 손실(Semiconductor Loss), 드라이버 동작(Driver Behavior), 부하 특성, 열 조건, 특정 SSR 아키텍처에 의해 제한된다.

기계적 접점이 없기 때문에 SSR은 전기적 및 열적 한계 내에서 동작할 경우 매우 높은 스위칭 내구성(Switching Endurance)을 제공한다. 접점 침식(Contact Erosion), 기계식 스프링 피로(Mechanical Spring Fatigue), 반복적인 접점 아크(Contact Arcing)가 발생하지 않으므로 빈번한 스위칭이 필요한 응용 분야에 적합하다. 그러나 반도체 접합부 온도, 과도 전압, 과전류 이벤트(Overcurrent Event), 절연 노화(Insulation Aging), 반복적인 열 사이클링(Thermal Cycling)이 신뢰성을 점진적으로 감소시킬 수 있으므로 수명이 무한한 것은 아니다.

유도성 부하(Inductive Load)는 SSR에서도 중요한 설계 고려사항이다. 모터, 솔레노이드, 전자기 브레이크(Electromagnetic Brake), 밸브(Valve), 릴레이 코일은 자기장에 에너지를 저장한다. 전류가 차단되면 이러한 에너지가 SSR 출력 정격을 초과하는 과도 전압을 발생시킬 수 있다. 따라서 출력 소자의 종류와 부하에 따라 플라이백 경로(Flyback Path), 과도 전압 억제기(Transient Voltage Suppressor), 스너버(Snubber) 또는 기타 보호 네트워크(Protective Network)를 이용한 적절한 억제 대책이 필요할 수 있다.

용량성 부하(Capacitive Load)는 초기 방전 상태의 커패시턴스가 연결되는 순간 큰 충전 전류(Charging Current)를 요구할 수 있기 때문에 다른 문제를 발생시킨다. 이러한 돌입 전류(Inrush Current)는 정상 상태 부하 전류보다 훨씬 클 수 있으며 연속 전류 정격이 충분해 보이는 SSR도 과도한 스트레스를 받을 수 있다. 따라서 전원 공급 장치(Power Supply), DC 링크 커패시터(DC-Link Capacitor), 전자 모듈(Electronic Module), 입력 필터(Input Filter)는 정격 동작 전류뿐 아니라 기동 시 동작 특성을 기준으로 평가해야 한다.

단락 동작(Short-Circuit Behavior)은 특히 중요하다. 반도체 스위치는 심각한 고장 전류(Fault Current)가 발생할 경우 기계식 릴레이 접점보다 훨씬 빠르게 손상될 수 있기 때문이다. 일반적으로 SSR이 외부 단락으로부터 스스로를 보호한다고 가정해서는 안 된다. 고장 에너지가 반도체의 허용 가능한 전기적·열적 한계 내에 유지되도록 적절하게 협조된 퓨즈(Fuse), 회로 차단기(Circuit Breaker), 전자식 전류 제한(Electronic Current Limiting) 또는 기타 보호 장치를 적용해야 한다.

SSR은 개방 상태 또는 도통 상태로 고장날 수 있지만, 출력이 단락되거나 영구적으로 도통되는 고장(Permanently Conducting Failure)은 반드시 고려해야 하는 중요한 고장 모드(Failure Mode)이다. 따라서 장치 고장 이후에는 OFF를 요구하는 제어 명령이 부하의 실제 차단을 보장하지 않는다. 안전 관련 시스템(Safety-Related System)에서는 요구되는 고장 대응(Fault Response)을 달성하기 위해 독립적인 모니터링(Independent Monitoring), 이중화 스위칭(Redundant Switching), 피드백 신호(Feedback Signal), 또는 직렬 전자기계식 절연 소자(Series Electromechanical Isolation Element)가 필요할 수 있다.

로봇 전기 아키텍처(Robotic Electrical Architecture)에서 SSR은 히터, 조명, 팬, 펌프, 밸브, 보조 전자장치(Auxiliary Electronics) 및 빈번하거나 조용한 스위칭이 필요한 기타 부하를 제어하는 데 사용할 수 있다. 특히 많은 보조 서브시스템이 직류 전원 레일(DC Power Rail)에서 동작하기 때문에 MOSFET 기반 직류 스위칭은 배터리 구동 로봇과 자율이동로봇(Autonomous Mobile Robot, AMR)에서 중요하다. SSR은 저전력 제어기와 고전류 부하 사이의 인터페이스를 제공하면서 필요한 경우 입력과 출력 사이의 절연을 유지할 수 있다.

따라서 전자기계식 릴레이와 SSR 중 하나를 선정하려면 단순히 전류 정격만 비교하는 것이 아니라 시스템 수준 평가(System-Level Evaluation)가 필요하다. 전자기계식 릴레이는 낮은 폐접점 저항, 물리적인 접점 분리(Physical Contact Separation), 비교적 낮은 누설 전류를 제공하는 반면, SSR은 무소음 동작, 높은 스위칭 내구성, 빠른 응답, 접점 바운스가 없다는 장점을 제공한다. 반면 SSR에는 도통 손실, 열 관리(Thermal Management) 요구사항, 누설 전류 및 반도체 고유의 고장 동작이 존재한다.

신뢰성 있는 SSR 설계에서는 제어 입력 호환성(Control-Input Compatibility), 입력-출력 절연(Input-Output Isolation), 부하 전압, 연속 전류, 돌입 또는 서지 전류(Surge Current), 스위칭 주파수, 출력 소자 기술(Output-Device Technology), 오프상태 누설 전류, 도통 손실, 주변 온도, 냉각 조건(Cooling Condition), 과도 현상 보호(Transient Protection)를 평가해야 한다. 또한 반도체 출력은 보호 장치가 적절하게 협조되지 않을 경우 일반적인 과전류 보호 장치가 동작하기 전에 손상될 수 있으므로 퓨즈 또는 회로 차단기와의 보호 협조(Protection Coordination)도 필수적이다.

따라서 솔리드 스테이트 릴레이(Solid-State Relay)는 모든 전자기계식 릴레이를 직접 대체하는 단순한 전자식 릴레이가 아니라 반도체 전력 스위칭 어셈블리(Semiconductor Power-Switching Assembly)로 이해하는 것이 적절하다. 빈번한 스위칭, 무소음 동작, 빠른 응답, 진동 내성(Vibration Resistance), 긴 사이클 수명(Long Cycle Life)이 요구될 때 장점이 특히 커진다. 성공적인 적용을 위해서는 전기적 보호(Electrical Protection)와 열 공학(Thermal Engineering)이 필수적이며, 이는 이후 릴레이 코일 구동 회로(Relay Coil Drive Circuit), 접점 보호(Contact Protection), 스위칭 장치 신뢰성(Switching-Device Reliability)을 학습하기 위한 기반이 된다.

## 03.03. Coil Drive Circuit Design

![](images/image3.png){width="7.268055555555556in" height="7.268055555555556in"}

![](images/image4.png){width="7.268055555555556in" height="7.268055555555556in"}

릴레이 코일 구동 회로(Relay Coil Drive Circuit)는 저전력 제어 장치(Low-Power Control Device)와 릴레이의 전자기 코일(Electromagnetic Coil) 사이에 전기적 인터페이스(Electrical Interface)를 제공한다. 마이크로컨트롤러(Microcontroller), ECU, PLC 출력 및 논리 회로(Logic Circuit)는 일반적으로 릴레이 코일에 필요한 전류를 직접 공급할 수 없다. 따라서 트랜지스터(Transistor) 또는 MOSFET을 전자식 스위치(Electronic Switch)로 사용하여 제어기가 릴레이를 명령하고, 코일은 적절한 전원으로부터 필요한 전력을 공급받도록 구성한다.

첫 번째 설계 요구사항은 릴레이 코일 자체의 특성을 이해하는 것이다. 중요한 파라미터에는 정격 코일 전압(Nominal Coil Voltage), 코일 저항(Coil Resistance), 정격 코일 전력(Rated Coil Power), 동작 전압(Pickup Voltage), 복귀 전압(Dropout Voltage), 최대 허용 코일 전압(Maximum Allowable Coil Voltage)이 포함된다. 직류 코일(DC Coil)의 정상 상태 전류는 Icoil = Vcoil/Rcoil로 근사할 수 있으며, 이 전류는 스위칭 소자와 관련 배선에 요구되는 최소 전류 처리 능력을 결정한다.

일반적인 로우사이드 구동 회로(Low-Side Drive Circuit)는 릴레이 코일을 양의 전원과 스위칭 트랜지스터 사이에 배치한다. 트랜지스터는 코일과 접지(Ground) 사이에 연결되므로 트랜지스터를 활성화하면 전류 경로가 완성된다. 로우사이드 스위칭(Low-Side Switching)은 N채널 MOSFET(N-Channel MOSFET) 또는 NPN 바이폴라 접합 트랜지스터(NPN Bipolar Junction Transistor)를 마이크로컨트롤러나 다른 전자 제어기의 접지 기준 논리 신호(Ground-Referenced Logic)로 편리하게 제어할 수 있기 때문에 널리 사용된다.

NPN 바이폴라 접합 트랜지스터(NPN Bipolar Junction Transistor)는 간단하고 경제적인 릴레이 드라이버(Relay Driver)를 구현할 수 있다. 트랜지스터는 일반적으로 포화 영역(Saturation)에서 동작하도록 하여 릴레이가 여자되는 동안 컬렉터-이미터 전압(Collector-to-Emitter Voltage)을 낮게 유지한다. 베이스 저항(Base Resistor)은 제어기 출력에서 흐르는 전류를 제한하면서 신뢰성 있는 포화 동작에 충분한 베이스 구동 전류(Base Drive Current)를 제공해야 한다. 제어기 핀의 전류 공급 능력, 트랜지스터 전류 이득, 코일 전류 및 최악 조건(Worst-Case Operating Conditions)을 모두 고려해야 한다.

MOSFET은 정상 상태 게이트 전류(Steady-State Gate Current)가 매우 작고 낮은 도통 손실(Conduction Loss)을 제공할 수 있기 때문에 직류 릴레이 구동 회로에서 점점 더 선호된다. 로직 레벨 N채널 MOSFET(Logic-Level N-Channel MOSFET)은 규정된 게이트 특성이 적합하다면 3.3 V 또는 5 V 논리 신호로 직접 구동할 수 있다. 소자 선정은 단순히 MOSFET 문턱 전압(Threshold Voltage)만을 기준으로 하지 않고 실제 게이트 전압에서 보장되는 온저항(RDS(on))을 기준으로 해야 한다.

MOSFET의 전압 정격(Voltage Rating)은 릴레이 전원 전압과 예상되는 과도 조건(Transient Condition)을 충분한 여유를 두고 초과해야 한다. 전류 정격(Current Rating) 역시 적절한 열적·신뢰성 여유를 포함하여 코일 전류보다 높아야 한다. 릴레이 코일은 일반적으로 비교적 작은 전류를 요구하지만 자동차 및 로봇 전기 환경에서는 상당한 전원 변동(Supply Disturbance)이 발생할 수 있다. 따라서 전압 정격, 애벌랜치 능력(Avalanche Capability), 온도, 패키지 방열(Package Dissipation), 과도 현상 보호(Transient Protection)를 함께 평가해야 한다.

릴레이 코일은 전류가 흐르는 동안 자기장에 에너지를 저장하기 때문에 유도성 부하(Inductive Load)로 동작한다. 저장 에너지는 E = 1/2 LI²로 근사할 수 있으며, 여기서 L은 코일 인덕턴스(Coil Inductance), I는 코일 전류이다. 스위칭 트랜지스터가 갑자기 턴오프되면 코일은 기존 전류를 계속 유지하려 한다. 제어된 방전 경로(Controlled Discharge Path)가 없다면 이러한 특성으로 인해 스위칭 소자 양단에 높은 전압이 발생하여 전기적 과스트레스(Electrical Overstress)를 일으킬 수 있다.

플라이백 다이오드(Flyback Diode)는 직류 릴레이 코일에 적용할 수 있는 가장 단순한 억제 방법(Suppression Method)이다. 정상적인 여자 동작 중에는 역바이어스(Reverse Bias)가 되도록 코일 양단에 연결한다. 트랜지스터가 턴오프되면 코일 전류가 다이오드를 통해 다시 흐르면서 저장된 자기 에너지가 안전하게 감소한다. 다이오드는 스위칭 전압을 낮은 수준으로 클램핑(Clamping)하여 유도성 턴오프 과도 현상으로부터 트랜지스터를 효과적으로 보호한다.

단순한 플라이백 다이오드의 주요 단점은 릴레이 복귀(Release)가 느려진다는 것이다. 다이오드가 코일 전압을 비교적 낮은 값으로 제한하기 때문에 전류가 서서히 감소하고 자기장이 더 오랫동안 유지된다. 따라서 아마추어(Armature)가 비여자 위치로 복귀하는 데 추가적인 시간이 필요하다. 빠른 접점 개방이 중요한 응용 분야에서는 이러한 복귀 지연(Release Delay)이 제어 타이밍, 고장 절연(Fault Isolation), 접점 아크(Contact Arcing) 특성에 영향을 줄 수 있다.

더 높은 전압을 허용하는 억제 방식(Higher-Voltage Suppression Method)을 사용하면 코일 전류의 감소 속도를 높일 수 있다. 제너 다이오드(Zener Diode), 과도 전압 억제기(Transient Voltage Suppressor, TVS), 다이오드-제너 네트워크(Diode-Plus-Zener Network), 적절한 능동 클램프(Active Clamp)는 턴오프 시 코일 전압이 전원 전압보다 높아지는 것을 허용하면서 안전한 수준으로 제한한다. 더 높은 역전압은 자기 에너지를 빠르게 소산시켜 일반적인 플라이백 다이오드보다 빠른 릴레이 복귀를 가능하게 한다.

따라서 억제 방식의 선정은 반도체 보호(Semiconductor Protection)와 릴레이 복귀 성능(Relay Release Performance) 사이의 절충이다. 낮은 클램프 전압(Clamp Voltage)은 드라이버의 전기적 스트레스를 최소화하지만 복귀 시간을 증가시키며, 높은 클램프 전압은 복귀 시간을 단축하지만 전압 스트레스를 증가시킨다. 선정된 클램프 수준은 스위칭 소자의 정격보다 충분히 낮으면서 릴레이 타이밍, 전자기 적합성(Electromagnetic Compatibility, EMC), 시스템 안전 요구사항을 충족해야 한다.

게이트 저항(Gate Resistor)은 제어기와 MOSFET 게이트 사이에 자주 사용된다. MOSFET은 직류 상태에서는 게이트 전류가 거의 필요하지 않지만 게이트 커패시턴스(Gate Capacitance)로 인해 스위칭 순간에는 과도 전류가 흐른다. 게이트 저항은 피크 게이트 전류(Peak Gate Current)를 제한하고 스위칭 속도를 제어하며 링잉(Ringing)이나 전자기 방출(Electromagnetic Emission)을 줄일 수 있다. 또한 게이트-소스 풀다운 저항(Gate-to-Source Pull-Down Resistor)을 추가하여 제어기 출력이 기동 또는 리셋 과정에서 부동 상태(Floating)가 되더라도 MOSFET이 확실하게 OFF 상태를 유지하도록 한다.

NPN 트랜지스터 드라이버에서는 이에 대응하는 설계 요소로 베이스 저항(Base Resistor)과 필요한 경우 베이스-이미터 풀다운 저항(Base-Emitter Pull-Down Resistor)을 사용한다. 베이스 저항은 논리 출력에서 과도한 전류가 흐르는 것을 방지하고, 풀다운 저항은 제어기 핀 상태가 정의되지 않았을 때 트랜지스터가 의도하지 않게 활성화되는 것을 방지한다. 이러한 작은 부품들은 프로세서 기동 과정에서 제어되지 않은 릴레이 동작이 바람직하지 않거나 위험한 시스템 동작을 발생시킬 수 있기 때문에 중요하다.

시스템 아키텍처에서 부하 또는 코일의 리턴 경로(Return Path)를 항상 접지에 연결해야 하는 경우 하이사이드 릴레이 구동(High-Side Relay Driving)이 필요할 수 있다. 하이사이드 스위칭(High-Side Switching)은 P채널 MOSFET(P-Channel MOSFET), PNP 트랜지스터(PNP Transistor), 전용 하이사이드 드라이버 집적회로(Dedicated High-Side Driver IC)를 사용할 수 있다. 최신 보호형 하이사이드 드라이버(Protected High-Side Driver)는 전류 제한(Current Limiting), 열 차단(Thermal Shutdown), 개방 부하 감지(Open-Load Detection), 단락 진단(Short-Circuit Diagnostics), ECU와의 통신 기능을 추가로 제공할 수 있다.

제어기 영역(Controller Domain)을 릴레이 전력 영역(Relay Power Domain)으로부터 갈바닉 절연해야 하는 경우 전기적 절연(Electrical Isolation)을 추가할 수 있다. 옵토커플러(Optocoupler), 디지털 절연기(Digital Isolator), 절연 드라이버(Isolated Driver)를 사용하여 절연 경계를 넘어 제어 명령을 전달할 수 있다. 접지 전위차(Ground Potential Difference), 노이즈, 안전 요구사항 또는 서로 다른 전력 영역이 존재하는 경우 절연이 유용할 수 있지만, 릴레이 접점 자체도 코일 회로와 스위칭 부하 회로 사이의 절연을 제공한다.

릴레이의 동작 전압은 실제 코일 전압에 의존하기 때문에 전원 전압 변동(Supply-Voltage Variation)을 고려해야 한다. 배터리 구동 로봇과 차량에서는 기동 또는 높은 부하 상태에서 저전압(Undervoltage)이 발생할 수 있고 충전 중에는 높은 전압이 나타날 수 있다. 드라이버는 코일에 과도한 전압을 인가하지 않으면서 신뢰성 있는 동작에 충분한 전압을 보장해야 한다. 하네스 전압 강하(Harness Voltage Drop), 커넥터 저항(Connector Resistance), 트랜지스터 전압 강하, 접지 경로 저항(Ground-Path Resistance)을 최악 조건 분석에 포함해야 한다.

코일을 지속적으로 여자하면 코일 발열(Coil Heating)과 드라이버 손실(Driver Loss)이 모두 발생한다. MOSFET의 도통 손실은 P = I²RDS(on)으로 근사할 수 있으며, 바이폴라 트랜지스터(Bipolar Transistor)의 손실은 대략 VCE(sat) × I로 계산할 수 있다. 이러한 손실은 일반적으로 코일 전력보다 작지만 다수의 릴레이 채널을 포함하는 소형 전자 모듈(Compact Electronic Module)에서는 중요해질 수 있다. 따라서 주변 온도와 외함의 열적 조건(Thermal Condition)을 설계에 포함해야 한다.

펄스 폭 변조(Pulse-Width Modulation, PWM)를 사용하면 초기 동작 이후 릴레이의 유지 전력(Holding Power)을 줄일 수 있는 경우가 있다. 먼저 코일을 강하게 구동하여 아마추어를 움직인 후 평균 전류를 낮추면서 필요한 유지 조건 이상을 유지한다. 이 방법은 코일 온도와 시스템 전력 소비를 줄일 수 있지만, 특정 릴레이에 대해 PWM 주파수, 전류 리플(Current Ripple), 음향 특성(Acoustic Behavior), 전자기 방출, 보장된 유지력(Holding Force)을 검증해야 한다.

고급 릴레이 구동 회로에서는 진단 기능(Diagnostic Capability)이 유용하다. 코일 전류나 드라이버 전압을 모니터링하면 코일 단선(Open Coil), 배선 분리(Disconnected Wiring), 단락, 드라이버 고장 또는 예상하지 못한 전기적 상태를 식별하는 데 도움이 된다. 지능형 로우사이드 및 하이사이드 드라이버 IC(Intelligent Low-Side and High-Side Driver IC)는 이러한 진단 기능을 통합하는 경우가 많다. 그러나 코일 전류가 존재한다는 전기적 확인만으로 릴레이 접점이 실제로 명령된 상태로 전환되었다는 것을 증명할 수는 없다.

안전 관련 설계(Safety-Related Design)에서는 릴레이에 명령을 전달하는 것과 그 결과로 형성된 전력 상태를 확인하는 것을 구분해야 한다. 접점 용착(Welded Contact), 기계적으로 고착된 아마추어(Mechanically Stuck Armature), 파손된 링크(Broken Linkage), 열화된 접점(Degraded Contact)은 코일 드라이버가 정상적으로 동작하더라도 예상된 스위칭 동작을 방해할 수 있다. 높은 진단 범위(Diagnostic Coverage)가 필요한 시스템에서는 코일 구동 신호 외에도 스위칭 측 전압, 보조 접점(Auxiliary Contact), 부하 전류 또는 기타 독립적인 피드백(Independent Feedback)을 모니터링할 수 있다.

보호 협조(Protection Coordination)에서는 릴레이 드라이버, 코일 전원 배선, 커넥터, 퓨즈(Fuse), 상위 전력 분배 시스템(Upstream Power Distribution System)을 함께 고려해야 한다. 코일 단락이나 하네스 고장은 정상 코일 전류보다 훨씬 큰 전류를 발생시킬 수 있으므로 분기 회로(Branch Circuit)를 적절하게 보호해야 한다. 특정 고장 조건에서는 반도체 드라이버의 손상 임계시간이 상위 퓨즈의 동작 시간보다 훨씬 짧을 수 있기 때문에 반도체 드라이버 자체에도 국부적인 보호(Local Protection)가 필요할 수 있다.

전자기 적합성(Electromagnetic Compatibility, EMC)도 중요한 설계 고려사항이다. 릴레이 코일 스위칭은 전류와 전압의 급격한 변화를 발생시키며, 접점 스위칭 역시 전기 시스템에 추가적인 교란(Disturbance)을 유발할 수 있다. 억제 부품(Suppression Component)은 짧은 전류 경로를 갖도록 배치하고 접지를 신중하게 제어해야 하며, 민감한 논리 신호 배선은 노이즈가 많은 스위칭 경로와 분리해야 한다. 따라서 인쇄회로기판 배치(PCB Layout)는 부품 선정만큼 중요할 수 있다.

로봇 및 자율이동로봇(Autonomous Mobile Robot, AMR)의 전기 아키텍처에서 릴레이 드라이버는 일반적으로 MCU 또는 엣지 제어 전자장치(Edge-Control Electronics)를 보조 서브시스템, 센서, 펌프, 팬, 조명, 브레이크(Brake), 활성화 회로(Enable Circuit)를 제어하는 전력 분배 릴레이(Power-Distribution Relay)와 연결한다. 신뢰성 있는 동작을 위해서는 논리 영역(Logic Domain), 드라이버단(Driver Stage), 코일 전원, 보호 네트워크(Protection Network), 릴레이, 피드백 메커니즘(Feedback Mechanism)을 서로 독립된 부품이 아니라 하나의 통합된 제어 경로(Coordinated Control Path)로 다루어야 한다.

견고한 코일 구동 회로(Robust Coil Drive Circuit)는 궁극적으로 올바른 트랜지스터 선정, 충분한 전류 처리 능력, 과도 현상 억제(Transient Suppression), 정의된 기동 동작(Defined Startup Behavior), 열적 여유(Thermal Margin), 고장 보호(Fault Protection), 적절한 진단 기능을 결합해야 한다. 설계는 최소 전원 조건에서도 릴레이의 확실한 동작을 보장하고 복귀 및 비정상 상황에서 스위칭 전자장치를 보호해야 한다. 이러한 원리는 신뢰성 있는 릴레이 제어의 전기적 기반을 제공하며 이후 접점 보호(Contact Protection)와 수명 공학(Lifetime Engineering)을 이해하기 위한 기초가 된다.

## 03.04. Contact Protection and Snubber

![](images/image5.png){width="7.268055555555556in" height="7.268055555555556in"}

접점 보호(Contact Protection)는 전류가 차단되거나 연결될 때마다 전기 접점(Electrical Contact)이 심각한 스트레스를 받기 때문에 릴레이 설계(Relay Design)의 핵심 요소이다. 특히 유도성 부하(Inductive Load)와 용량성 부하(Capacitive Load)에서는 저장된 에너지(Stored Energy) 또는 돌입 전류(Inrush Current)로 인해 정상 상태 동작(Steady-State Operation)을 크게 초과하는 조건이 발생할 수 있다. 보호 회로(Protection Circuit)는 아크(Arcing), 접점 침식(Contact Erosion), 전자기 간섭(Electromagnetic Interference, EMI), 조기 릴레이 고장(Premature Relay Failure)을 감소시킨다.

릴레이 접점이 유도성 회로(Inductive Circuit)를 개방할 때 부하의 자기장에 에너지가 저장되어 있기 때문에 전류는 순간적으로 감소할 수 없다. 인덕턴스(Inductance)는 v = L(di/dt)의 관계에 따라 전류를 계속 유지하려 하며, 이로 인해 분리되는 접점 양단에 매우 높은 전압이 발생할 수 있다. 이 전압이 점차 넓어지는 접점 간극(Contact Gap)의 절연 내력(Dielectric Strength)을 초과하면 전기 아크(Electrical Arc)가 형성되고 이온화된 기체(Ionized Gas)를 통해 전류가 계속 흐르게 된다.

접점 아크(Contact Arcing)는 매우 높은 국부 온도(Localized Temperature)를 발생시켜 매번 스위칭할 때마다 소량의 접점 재료(Contact Material)를 용융, 증발 또는 이동시킬 수 있다. 반복되는 아크는 접점 표면을 점진적으로 변화시켜 표면 거칠기와 접점 저항(Contact Resistance)을 증가시킨다. 심각한 경우 재료 이동(Material Transfer), 피팅(Pitting), 산화(Oxidation), 접점 용착(Contact Welding)이 발생할 수 있다. 이러한 메커니즘으로 인해 릴레이의 전기적 수명(Electrical Life)은 일반적으로 기계적 수명(Mechanical Life)보다 훨씬 짧다.

따라서 접점 보호는 접점이 개방될 때 접점 양단에 나타날 에너지를 다른 경로로 전달하거나 제어된 방식으로 소산시키는 것을 목표로 한다. 일반적인 방법에는 RC 스너버(RC Snubber), 플라이백 다이오드(Flyback Diode), 과도 전압 억제기(Transient Voltage Suppressor, TVS), 제너 클램프(Zener Clamp), 금속 산화물 배리스터(Metal-Oxide Varistor, MOV) 및 이들을 조합한 회로가 있다. 적절한 방식은 교류(AC) 또는 직류(DC) 여부와 부하 전압, 전류, 인덕턴스, 스위칭 속도 및 요구되는 복귀 동작에 따라 결정된다.

RC 스너버(RC Snubber)는 직렬로 연결된 저항(Resistor)과 커패시터(Capacitor)로 구성되며 릴레이 접점 양단 또는 일부 응용에서는 스위칭되는 부하 양단에 연결한다. 접점이 개방되기 시작하면 커패시터가 접점 간극의 전압을 빠르게 상승시키는 전류를 일시적으로 받아들인다. 이를 통해 접점 양단의 전압 상승률(Rate of Voltage Rise)을 제한하며, 저항은 커패시터의 충전 및 방전 전류를 제어하고 저장된 에너지의 일부를 소산한다.

커패시터 값(Capacitor Value)은 RC 스너버의 효과에 큰 영향을 미친다. 큰 커패시턴스(Capacitance)는 더 많은 과도 에너지(Transient Energy)를 흡수하고 전압 상승률을 효과적으로 감소시킬 수 있지만, 접점이 닫힐 때 더 큰 과도 전류를 허용한다. 따라서 지나치게 큰 커패시턴스는 접점 스트레스를 제거하기보다 추가적인 스트레스를 발생시킬 수 있다. 커패시터는 반복적인 펄스 동작(Repetitive Pulse Operation)에 적합한 전압 정격과 구조를 가져야 한다.

스너버의 저항은 피크 전류(Peak Current)를 제한하고 회로 인덕턴스와 커패시턴스 사이에서 발생하는 진동(Oscillation)을 감쇠한다. 저항이 너무 작으면 접점이 닫힐 때 커패시터의 방전으로 인해 접점을 통과하는 높은 전류 펄스가 발생할 수 있다. 반대로 저항이 너무 크면 스너버가 과도 전압을 충분히 제어하지 못할 수 있다. 따라서 RC 값은 전기적 절충(Electrical Compromise)을 통해 선정해야 하며 대표적인 부하 조건에서 측정을 통해 검증하는 것이 바람직하다.

RC 스너버를 접점 양단에 직접 배치하면 접점이 분리될 때 발생하는 전압을 제한하여 접점 간극을 보호할 수 있다. 그러나 이러한 구성에서는 직렬 RC 네트워크(Series RC Network)를 통해 개방된 접점을 우회하는 작은 전류 경로가 형성된다. 일부 회로에서는 이러한 누설 경로(Leakage Path)가 고임피던스 부하(High-Impedance Load) 또는 민감한 전자장치에 영향을 줄 수 있다. 스너버를 부하 양단에 배치하면 이러한 영향의 일부를 줄일 수 있지만 과도 에너지가 시스템 내부에서 순환하는 방식이 달라진다.

직류 유도성 부하(DC Inductive Load)에서는 부하 양단에 직접 연결한 플라이백 다이오드가 가장 효과적인 억제 방법 중 하나이다. 정상 동작 중에는 다이오드가 역바이어스(Reverse Bias)되어 전류가 흐르지 않는다. 릴레이가 개방되면 유도성 전류가 다이오드로 전환되어 저장된 자기 에너지(Magnetic Energy)가 감소할 때까지 부하를 통해 순환한다. 이에 따라 접점 전압이 크게 감소하여 아크와 전기적 노이즈(Electrical Noise)를 효과적으로 억제한다.

플라이백 다이오드의 낮은 클램프 전압(Clamp Voltage)은 유도성 전류가 천천히 감소하도록 만든다. 솔레노이드(Solenoid), 전자기 브레이크(Electromagnetic Brake), 밸브(Valve) 및 기타 액추에이터(Actuator)에서는 이로 인해 기계적 복귀(Mechanical Release)가 지연될 수 있다. 예를 들어 전원이 제거된 직후 즉시 작동해야 하는 브레이크는 단순한 다이오드 억제를 사용할 경우 너무 느리게 반응할 수 있다. 따라서 접점 보호는 제어되는 액추에이터의 동적 거동(Dynamic Behavior)과 함께 평가해야 한다.

다이오드와 제너 다이오드(Zener Diode) 또는 과도 전압 억제기를 조합하면 전류가 감소하는 동안 더 높은 제어 전압을 허용할 수 있다. 높은 클램프 전압은 di/dt를 증가시켜 자기 에너지를 더 빠르게 제거하므로 액추에이터 또는 릴레이의 복귀 시간을 개선하면서도 최대 전압을 제한한다. 이 방식은 직류 시스템에서 강력한 접점 보호와 빠른 부하 비여자(Load De-Energization) 사이에 유용한 절충안을 제공한다.

과도 전압 억제기(Transient Voltage Suppressor, TVS)는 지정된 전압 이상에서 제어된 애벌랜치 도통(Controlled Avalanche Conduction)을 시작하여 짧은 시간 동안 발생하는 전압 스파이크(Voltage Spike)를 클램핑할 수 있다. TVS는 단방향(Unidirectional) 및 양방향(Bidirectional) 구성으로 제공되며 직류 또는 적절한 교류 과도 현상 억제에 사용할 수 있다. 선정 시 스탠드오프 전압(Standoff Voltage), 항복 전압(Breakdown Voltage), 클램프 전압, 펄스 에너지(Pulse Energy), 반복 동작 및 주변 부품의 내전압 능력을 고려해야 한다.

금속 산화물 배리스터(Metal-Oxide Varistor, MOV) 역시 과도 현상 억제에 널리 사용되며 특히 교류 회로에서 많이 적용된다. 인가 전압이 특정 수준을 초과하면 저항이 급격히 감소하여 과도 전류가 흐르도록 하고 피크 전압을 제한한다. MOV는 상당한 서지 에너지(Surge Energy)를 흡수할 수 있지만 반복적인 고에너지 이벤트에 의해 특성이 점진적으로 열화된다. 따라서 반복적인 릴레이 스위칭 응용에서는 MOV의 수명과 고장 동작(Failure Behavior)을 고려해야 한다.

교류 유도성 부하(AC Inductive Load)는 전류 방향이 매 반주기마다 반전되므로 단순한 직류 부하와 다른 방식으로 처리해야 한다. 단일 플라이백 다이오드는 전원 파형의 한쪽 극성에서 도통하게 되므로 일반적으로 교류 부하 양단에 사용할 수 없다. 따라서 교류 릴레이 응용에서는 RC 스너버, 양방향 TVS(Bidirectional TVS), MOV 또는 적절하게 설계된 억제 네트워크(Suppression Network)를 사용하여 스위칭 과도 현상을 제한한다.

용량성 부하(Capacitive Load)는 개방보다 접점이 닫히는 순간 가장 큰 스트레스를 발생시킨다. 초기 방전 상태의 커패시터는 거의 단락 회로처럼 동작할 수 있으며, 전원 임피던스(Source Impedance), 배선 저항(Wiring Resistance), 등가 직렬 저항(Equivalent Series Resistance, ESR)에 의해서만 제한되는 큰 돌입 전류가 발생할 수 있다. 반복적인 고전류 접점 폐쇄는 접점 바운스 아크(Contact Bounce Arcing), 표면 손상 및 용착을 일으킬 수 있으므로 용량성 부하의 접점 보호에서는 돌입 전류 관리가 중요하다.

돌입 전류 제한(Inrush Limiting)은 직렬 저항(Series Resistance), 부온도계수 서미스터(Negative-Temperature-Coefficient Thermistor, NTC), 프리차지 회로(Pre-Charge Circuit), 제어형 반도체 스위치(Controlled Semiconductor Switch), 단계적 릴레이 동작(Staged Relay Operation)을 사용하여 구현할 수 있다. 대형 DC 링크 커패시터(DC-Link Capacitor)는 일반적으로 메인 릴레이 또는 컨택터가 닫히기 전에 프리차지 저항을 통해 충전한다. 커패시터 전압이 전원 전압에 가까워진 후 메인 접점을 닫으면 훨씬 낮은 전류 스트레스로 연결할 수 있어 용착 위험을 크게 줄이고 접점 수명을 연장할 수 있다.

모터 부하(Motor Load)는 여러 가지 까다로운 스위칭 특성을 동시에 가진다. 기동 시 정지 상태의 모터는 역기전력(Back Electromotive Force)이 아직 형성되지 않았기 때문에 정상 동작 전류보다 몇 배 높은 전류를 소비할 수 있다. 전류 차단 시에는 권선 인덕턴스(Winding Inductance)가 상당한 과도 전압을 발생시킬 수 있다. 따라서 모터를 스위칭하는 릴레이는 접점 폐쇄 시의 돌입 전류와 개방 시의 유도성 에너지를 모두 견뎌야 하며, 모터 부하 정격(Motor-Load Rating)은 저항성 부하 정격(Resistive-Load Rating)보다 훨씬 낮을 수 있다.

스너버 설계(Snubber Design)에서는 전자기 적합성(Electromagnetic Compatibility, EMC)도 고려해야 한다. 접점 아크는 넓은 주파수 범위의 전자기 노이즈(Broadband Electromagnetic Noise)를 발생시키며 전도 및 방사 경로를 통해 인접한 센서, 통신 및 제어기 회로에 결합될 수 있다. 전압 상승률과 아크 지속시간을 제한하면 이러한 교란을 발생원에서 감소시킬 수 있다. 짧은 억제 전류 루프, 적절한 접지, 신중한 하네스 라우팅(Harness Routing), 민감한 신호 회로와의 물리적 분리는 EMC 성능을 더욱 향상시킨다.

릴레이와 부하 사이의 배선에도 인덕턴스가 존재하기 때문에 억제 소자(Suppression Device)의 위치가 중요하다. 에너지원에서 멀리 떨어진 보호 소자는 연결 하네스 자체에도 자기 에너지가 저장되므로 국부적인 전압을 충분히 클램핑하지 못할 수 있다. 유도성 부하에서는 의도된 에너지 순환 경로(Energy Circulation Path)와 시스템 아키텍처에 따라 보호 소자를 부하 또는 스위칭 소자에 가깝게 배치하는 것이 일반적으로 가장 효과적이다.

부품 정격(Component Rating)은 단일 과도 이벤트뿐만 아니라 반복 동작에 충분한 여유를 포함해야 한다. 스너버 커패시터는 반복적인 충·방전 펄스를 경험하고, 저항은 펄스 에너지를 소산하며, TVS 또는 MOV는 스위칭 과정에서 과도 에너지를 흡수한다. 주변 온도(Ambient Temperature), 스위칭 주파수(Switching Frequency), 부품 공차(Component Tolerance), 부하 변화 및 비정상 조건은 누적되는 열적·전기적 스트레스를 크게 변화시킬 수 있다.

보호 부품 자체도 새로운 고장 모드(Failure Mode)를 발생시킬 수 있다. 단락된 억제 커패시터, 고장난 TVS, 열화된 MOV 또는 잘못 선정된 다이오드는 부하 동작에 영향을 주거나 과도한 전류를 발생시킬 수 있다. 따라서 안전 관련 설계(Safety-Related Design)에서는 보호 소자의 고장이 부하를 의도하지 않게 여자시키거나 절연을 무력화하고 배선을 과부하시키거나 필요한 액추에이터 복귀를 방해할 가능성을 고려해야 한다. 이에 따라 적절한 퓨즈 협조(Fuse Coordination)와 진단 범위(Diagnostic Coverage)가 필요할 수 있다.

오실로스코프 측정(Oscilloscope Measurement)은 접점 보호를 검증할 때 특히 유용하다. 대표적인 개방 및 폐쇄 동작 동안 접점 또는 부하 양단의 전압을 관찰하면서 관련 전류 동작을 함께 모니터링해야 한다. 이후 억제 회로 적용 전후의 피크 전압(Peak Voltage), 링잉(Ringing), 아크 지속시간(Arc Duration), 전류 감소(Current Decay), 복귀 타이밍(Release Timing), 반복 발열(Repetitive Heating)을 비교할 수 있다. 이러한 측정은 공칭 부품 계산에만 의존하는 것보다 높은 설계 신뢰도를 제공한다.

로봇 및 자율이동로봇(Autonomous Mobile Robot, AMR)의 전력 시스템에서 릴레이 접점은 펌프, 팬, 브레이크, 솔레노이드, 조명, 히터, 전력 변환기(Power Converter), 보조 전자 모듈(Auxiliary Electronic Module)을 스위칭할 수 있다. 각각의 부하는 서로 다른 과도 특성(Transient Signature)을 가지므로 하나의 범용 스너버 설계가 모든 채널을 보호할 수 있다고 가정해서는 안 된다. 각 전력 분배 분기(Power-Distribution Branch)의 부하 분류와 실제 측정된 스위칭 특성을 기준으로 억제 및 돌입 전류 관리 방법을 선정해야 한다.

신뢰성 있는 접점 보호는 궁극적으로 전기 에너지가 어디에 저장되는지, 접점 상태가 변경될 때 그 에너지가 어떻게 이동하는지, 보호 네트워크가 에너지 방출을 어떻게 제어하는지를 이해하는 것에서 시작한다. 적절하게 설계된 스너버 또는 억제 회로는 허용할 수 없는 누설 전류나 복귀 지연을 발생시키지 않으면서 아크 에너지(Arc Energy), 전압 스트레스(Voltage Stress), EMI, 접점 침식, 용착 위험을 감소시킨다. 이러한 원리는 다음 단계의 릴레이 수명 및 신뢰성(Relay Lifetime and Reliability)을 향상시키기 위한 직접적인 기반이 된다.

## 03.05. Relay Lifetime and Reliability

![](images/image6.png){width="7.268055555555556in" height="7.268055555555556in"}

릴레이 수명 및 신뢰성(Relay Lifetime and Reliability)은 릴레이가 의도된 사용 기간(Service Period) 동안 요구되는 스위칭 기능(Switching Function)을 얼마나 일관되게 수행하는지를 나타낸다. 신뢰성은 릴레이의 공칭 전류 및 전압 정격뿐만 아니라 부하 유형(Load Type), 스위칭 주파수(Switching Frequency), 환경 조건(Environmental Conditions), 코일 여자(Coil Excitation), 접점 보호(Contact Protection), 고장 노출(Fault Exposure)에 의해 결정된다. 정상 상태 조건에서 적절한 정격을 가진 릴레이도 과도 스트레스(Transient Stress)를 무시하면 조기에 고장날 수 있다.

릴레이 수명(Relay Lifetime)은 일반적으로 기계적 수명(Mechanical Life)과 전기적 수명(Electrical Life)으로 구분한다. 기계적 수명은 접점에 전기 부하가 거의 또는 전혀 인가되지 않은 상태에서 기계 장치가 수행할 수 있는 스위칭 동작 횟수를 의미한다. 전기적 수명은 지정된 전기 부하를 스위칭하면서 수행할 수 있는 동작 횟수를 의미한다. 전기적 스위칭에서는 아크(Arcing), 발열(Heating), 침식(Erosion), 재료 이동(Material Transfer)이 발생하므로 전기적 수명은 일반적으로 기계적 수명보다 상당히 짧다.

기계적 마모(Mechanical Wear)는 아마추어(Armature), 복귀 스프링(Return Spring), 피벗(Pivot), 베어링(Bearing), 접점 지지부(Contact Support) 및 기타 가동 구조(Moving Structure)에서 발생한다. 반복적인 동작은 피로(Fatigue), 치수 변화(Dimensional Change), 마찰 증가(Friction Increase), 스프링 힘 감소(Loss of Spring Force)를 발생시킬 수 있다. 기계적 내구성(Mechanical Endurance)이 매우 많은 사이클에 도달할 수 있더라도 진동(Vibration), 충격(Shock), 오염(Contamination), 과도한 코일 전압, 부적절한 장착 조건은 단순한 동작 횟수에서 예상되는 것보다 빠르게 열화를 진행시킬 수 있다.

전기 접점 마모(Electrical Contact Wear)는 접점이 개방되고 닫힐 때 존재하는 에너지의 영향을 크게 받는다. 유도성 부하(Inductive Load)를 차단하면 저장된 자기 에너지(Stored Magnetic Energy)가 높은 전압을 발생시키고 분리되는 접점 사이에서 아크를 유지할 수 있다. 접점이 닫힐 때에는 용량성 부하(Capacitive Load)와 모터(Motor)가 큰 돌입 전류(Inrush Current)를 발생시킬 수 있다. 이러한 과도 현상은 부하 사양에 표시된 공칭 정상 상태 전류보다 훨씬 큰 스트레스를 가할 수 있다.

접점 아크(Contact Arcing)는 접점 재료(Contact Material)를 점진적으로 제거하거나 재분배한다. 각각의 스위칭 과정에서 소량의 금속이 용융(Melting), 증발(Vaporization), 산화(Oxidation)되거나 한 접점 표면에서 다른 접점 표면으로 이동할 수 있다. 많은 사이클이 반복되면 표면에 피트(Pit), 돌출부(Protrusion), 거칠기 증가 또는 형상 변화가 발생할 수 있다. 이러한 변화는 접점 저항(Contact Resistance)과 국부 전류 밀도(Local Current Density)에 영향을 주어 추가적인 열화를 가속하고 전기적 수명을 감소시킬 수 있다.

접점 용착(Contact Welding)은 가장 심각한 릴레이 고장 메커니즘(Relay Failure Mechanism) 중 하나이다. 접점 폐쇄 전류 또는 아크 에너지(Arc Energy)가 충분히 커지면 접점 표면이 국부적으로 녹아 서로 융착될 수 있다. 이 경우 코일이 비여자(De-Energized)된 후에도 릴레이가 전기적으로 닫힌 상태를 유지할 수 있다. 모터 기동 전류(Motor Startup Current), 커패시터 돌입 전류(Capacitor Inrush), 단락(Short Circuit), 접점 바운스(Contact Bounce), 불충분한 릴레이 정격은 모두 용착 위험을 증가시키므로 과도 전류 분석(Transient Current Analysis)이 필수적이다.

접점 저항(Contact Resistance)은 접점 상태를 나타내는 중요한 지표를 제공한다. 정상적인 폐접점(Closed Contact)은 일반적으로 낮은 저항을 가지지만 오염, 산화, 접촉력 감소(Reduced Contact Force), 침식 또는 표면 손상으로 인해 시간이 지나면서 저항이 증가할 수 있다. 전력 손실은 P = I²R의 관계를 따르므로 저항이 증가하면 높은 전류에서 추가적인 열이 발생한다. 이러한 발열은 접점 인터페이스(Contact Interface)를 더욱 손상시키고 노화를 가속하는 양의 피드백 메커니즘(Positive Feedback Mechanism)을 형성할 수 있다.

부하 유형(Load Type)은 예상 릴레이 수명에 큰 영향을 미친다. 저항성 부하(Resistive Load)는 일반적으로 비교적 예측 가능한 스위칭 스트레스를 발생시키지만 모터, 솔레노이드(Solenoid), 변압기(Transformer), 램프(Lamp), 커패시터(Capacitor), 전자식 전원 공급 장치(Electronic Power Supply)는 상당한 과도 동작을 발생시킬 수 있다. 따라서 특정 저항성 전류를 스위칭할 수 있는 릴레이도 유도성, 모터, 램프 또는 용량성 부하에 적용할 때는 상당한 디레이팅(Derating)이 필요할 수 있다.

스위칭 주파수(Switching Frequency)는 기계적 마모와 열적 조건(Thermal Conditions)에 모두 영향을 미친다. 하루에 몇 번만 동작하는 릴레이와 분당 여러 번 스위칭하는 릴레이는 매우 다른 노화 특성을 가진다. 빈번한 동작은 누적되는 아크 발생 횟수를 증가시키고 코일, 접점 또는 주변 구조가 열적 평형(Thermal Equilibrium)으로 복귀하는 것을 방해할 수 있다. 따라서 전기적 수명 계산에서는 시간당 예상 동작 횟수, 일일 듀티 사이클(Daily Duty Cycle), 전체 임무 기간(Total Mission Duration)을 고려해야 한다.

코일 조건(Coil Conditions)도 장기적인 신뢰성에 영향을 미친다. 지속적인 과전압(Overvoltage)은 코일 전류와 온도를 증가시켜 절연 노화(Insulation Aging)를 가속하고 주변 기계 부품에도 영향을 줄 수 있다. 저전압(Undervoltage) 역시 문제가 될 수 있는데, 불충분한 자기력(Magnetic Force)은 불완전한 동작(Incomplete Pickup), 채터링(Chatter), 접촉력 감소를 발생시킬 수 있기 때문이다. 따라서 규정된 동작 범위 내에서 안정적인 코일 여자 상태를 유지하는 것은 스위칭 성능과 릴레이 수명 모두에 중요하다.

코일 온도(Coil Temperature)는 전기적 전력 손실과 주변 열 환경(Thermal Environment)에 따라 결정된다. 구리 권선(Copper Winding)의 온도가 상승하면 저항이 증가하여 코일 전류와 전자기력(Electromagnetic Force)이 변화한다. 높은 주변 온도(Ambient Temperature)는 사용 가능한 열적 여유(Thermal Margin)를 감소시키고 절연재, 플라스틱, 접착제(Adhesive), 스프링 재료의 열화를 가속할 수 있다. 따라서 릴레이 선정에서는 실온 조건의 정격이 항상 적용된다고 가정하지 말고 제조업체가 제공하는 온도 의존 한계(Temperature-Dependent Limits)를 사용해야 한다.

접점 바운스(Contact Bounce)는 하나의 명령된 스위칭 과정에서도 각각의 짧은 분리와 재접촉이 추가적인 아크를 발생시킬 수 있기 때문에 전기적 노화(Electrical Aging)에 기여한다. 특히 접점이 닫힐 때 높은 돌입 전류가 존재하면 그 영향은 더욱 심각해진다. 바운스 동작의 상당 부분은 기계 설계(Mechanical Design)에 의해 결정되지만 그 전기적 심각성은 외부 회로 조건에 의해 결정된다. 따라서 적절한 부하 선정과 돌입 전류 제한(Inrush Limitation)을 통해 실제 접점 수명을 크게 향상시킬 수 있다.

접점 보호(Contact Protection)는 릴레이 신뢰성에 직접적인 영향을 미친다. 플라이백 다이오드(Flyback Diode), TVS 클램프(TVS Clamp), 제너 네트워크(Zener Network), RC 스너버(RC Snubber), MOV 및 기타 억제 소자(Suppression Device)는 리액티브 부하(Reactive Load)를 스위칭할 때 접점에 가해지는 전기 에너지를 감소시킨다. 효과적인 억제는 아크와 전자기 간섭(Electromagnetic Interference, EMI)을 크게 줄일 수 있다. 그러나 과도한 억제는 전류 감소를 늦추고 솔레노이드, 브레이크(Brake) 또는 기타 전자기 액추에이터(Electromagnetic Actuator)의 복귀를 지연시킬 수 있으므로 신중하게 선정해야 한다.

환경 오염(Environmental Contamination)은 접점 동작을 크게 변화시킬 수 있다. 먼지(Dust), 습기(Moisture), 부식성 가스(Corrosive Gas), 오일(Oil), 화학 증기(Chemical Vapor)는 노출된 표면을 열화시키거나 충분히 밀폐되지 않은 릴레이 내부로 침투할 수 있다. 특히 저전류 신호 접점(Low-Current Signal Contact)은 산화막이나 오염막을 제거할 만큼 충분한 전기 에너지가 없을 수 있으므로 더욱 민감하다. 따라서 설치 환경에 따라 밀폐형 릴레이(Sealed Relay), 플럭스 내성 릴레이(Flux-Resistant Relay) 또는 환경 보호형 릴레이(Environmentally Protected Relay)가 필요할 수 있다.

진동(Vibration)과 기계적 충격(Mechanical Shock)은 차량, 로봇, 자율이동로봇(Autonomous Mobile Robot, AMR), 산업 기계(Industrial Machine), 이동 장비(Mobile Equipment)에서 특히 중요하다. 외부 가속도(External Acceleration)는 아마추어나 접점 시스템을 교란하여 접촉력을 일시적으로 변화시키거나 의도하지 않은 개방과 폐쇄를 발생시킬 수 있다. 반복적인 진동은 단자(Terminal), 솔더 접합부(Solder Joint), 장착 구조(Mounting Structure), 내부 기계 요소에도 피로를 발생시킬 수 있다. 따라서 릴레이 검증(Relay Qualification)은 제품의 실제 기계적 환경을 반영해야 한다.

열 사이클링(Thermal Cycling)은 또 다른 신뢰성 메커니즘이다. 반복적인 가열과 냉각은 서로 다른 열팽창 계수(Coefficient of Thermal Expansion)를 가진 재료가 서로 다른 정도로 팽창하고 수축하도록 만든다. 장기간에 걸쳐 이러한 현상은 솔더 접합부, 단자, 코일 연결부, 플라스틱 구조 및 내부 인터페이스에 스트레스를 가할 수 있다. 따라서 빈번한 전원 사이클링(Power Cycling)이나 큰 주변 온도 변화가 존재하는 시스템에서는 최대 동작 온도뿐 아니라 열 사이클링도 고려해야 한다.

릴레이 디레이팅(Relay Derating)은 신뢰성 여유(Reliability Margin)를 향상시키는 효과적인 방법이다. 접점을 절대 정격 또는 공칭 정격에서 지속적으로 동작시키는 대신 추가적인 전압, 전류, 열 및 과도 현상 처리 능력을 가진 릴레이를 선정한다. 필요한 여유는 하나의 보편적인 비율이 아니라 부하 특성과 동작 환경에 따라 결정된다. 돌입 전류, 유도성 에너지(Inductive Energy), 주변 온도, 스위칭 주파수, 예상 사용 수명(Expected Service Life)을 기준으로 디레이팅 수준을 결정해야 한다.

신뢰성 평가(Reliability Evaluation)에서는 정상 동작 스트레스와 비정상 및 고장 조건(Abnormal and Fault Conditions)을 구분해야 한다. 정상적인 스위칭은 릴레이 정격 범위 내에 충분히 들어올 수 있지만 모터 스톨(Stalled Motor), 단락된 부하(Shorted Load), 고장난 전력 변환기(Failed Power Converter), 배선 고장(Wiring Fault)은 접점에 훨씬 큰 전류를 가할 수 있다. 따라서 상위 퓨즈(Fuse) 또는 회로 차단기(Circuit Breaker)는 보호 장치가 회로를 차단하기 전에 고장 에너지가 릴레이의 내량(Withstand Capability)을 초과하지 않도록 협조되어야 한다.

고장 모드(Failure Mode)에는 접점 용착, 접점 도통 불능(Failure to Conduct), 과도한 접점 저항, 간헐적 스위칭(Intermittent Switching), 코일 단선(Coil Open Circuit), 코일 단락(Coil Short Circuit), 기계적 고착(Mechanical Sticking), 스프링 힘 약화(Weakened Spring Force), 절연 열화(Insulation Degradation)가 포함될 수 있다. 이러한 고장은 모두 동일한 시스템 결과를 발생시키지 않는다. 따라서 신뢰성 공학(Reliability Engineering)에서는 각각의 고장 메커니즘 발생 가능성과 그 결과로 형성되는 릴레이 상태가 전체 시스템에 미치는 영향을 함께 고려해야 한다.

특히 고장 시 개방(Fail-Open)과 고장 시 폐쇄(Fail-Closed) 동작을 구분하는 것이 중요하다. 일부 릴레이 고장은 부하로 전류가 공급되지 않도록 만들지만 접점 용착은 부하를 계속 여자 상태로 유지할 수 있다. 안전 관련 회로(Safety-Related Circuit)에서는 후자의 상태가 특히 위험할 수 있다. 따라서 코일 전원을 제거하는 것만으로 부하 절연(Load Isolation)이 보장된다고 가정해서는 안 되며, 의도하지 않은 여자(Unintended Energization)의 결과가 심각한 경우 독립적인 피드백(Independent Feedback) 또는 이중화 차단(Redundant Disconnection)이 필요할 수 있다.

진단 모니터링(Diagnostic Monitoring)은 완전한 고장이 발생하기 전에 열화를 감지하여 시스템 수준 신뢰성(System-Level Reliability)을 향상시킬 수 있다. 코일 전류(Coil Current), 접점 측 전압(Contact-Side Voltage), 부하 전류(Load Current), 보조 접점(Auxiliary Contact), 온도, 스위칭 응답 시간(Switching Response Time)은 유용한 정보를 제공할 수 있다. 예를 들어 닫힌 접점 양단의 전압 강하가 증가하면 접점 저항이 증가하고 있음을 나타낼 수 있다. 그러나 진단 임계값(Diagnostic Threshold)은 전원 전압, 부하 전류, 온도 및 부품 공차(Component Tolerance)의 정상적인 변화를 고려해야 한다.

예방 정비(Preventive Maintenance)는 동작 사이클(Operating Cycle), 경과 사용 시간(Elapsed Service Time), 측정된 열화(Measured Degradation), 또는 이들을 조합한 기준으로 수행할 수 있다. 높은 사이클 응용에서는 릴레이 동작 횟수를 계산하는 것이 누적 사용량을 나타내는 실용적인 지표가 된다. 보다 고급 시스템에서는 사이클 횟수와 함께 스위칭 전류, 부하 유형, 온도 및 고장 이력을 조합하여 모든 스위칭 이벤트를 동일하게 취급하는 대신 실질적인 접점 스트레스(Effective Contact Stress)를 추정할 수 있다.

신뢰성 시험(Reliability Testing)은 단순히 데이터시트의 수명 값에 의존하지 않고 대표적인 실제 동작 조건을 재현해야 한다. 시험에는 실제적인 부하 전류, 돌입 조건, 유도성 에너지, 전원 전압, 온도, 진동 및 스위칭 주파수에서 반복적인 스위칭을 포함할 수 있다. 이후 접점 저항, 복귀 시간(Release Time), 동작 특성(Pickup Behavior), 온도 상승(Temperature Rise), 고장 발생을 모니터링하여 릴레이가 의도된 임무 프로파일(Mission Profile)을 만족하는지 판단할 수 있다.

가속 수명 시험(Accelerated Life Testing)은 증가된 스위칭 주파수, 온도, 전기적 스트레스 또는 환경적 가혹도(Environmental Severity)를 릴레이에 적용하여 실용적인 시험 기간 내에 지배적인 고장 메커니즘을 확인할 수 있도록 한다. 그러나 과도한 스트레스는 정상 사용 중에는 발생하지 않을 고장 메커니즘을 만들어낼 수 있으므로 가속 조건을 신중하게 적용해야 한다. 목적은 실제 응용과 의미 있는 상관관계를 유지하면서 관련 노화 과정(Aging Process)을 가속하는 것이다.

로봇 및 자율이동로봇(Autonomous Mobile Robot, AMR) 시스템에서 릴레이 신뢰성은 전력 분배(Power Distribution), 제동(Braking), 보조 액추에이터(Auxiliary Actuator), 펌프, 팬, 조명, 센서 및 서브시스템 활성화 기능(Subsystem Enable Function)에 직접적인 영향을 미친다. 따라서 릴레이 고장은 단순한 편의 기능의 상실에서부터 이동 능력 상실(Loss of Mobility) 또는 안전 관련 상태(Safety-Related Condition)에 이르기까지 다양한 결과를 발생시킬 수 있다. 릴레이 수명은 듀티 사이클, 환경 노출(Environmental Exposure), 정비 전략(Maintenance Strategy), 고장 대응(Fault Response)과 함께 시스템 임무 프로파일의 일부로 다루어야 한다.

신뢰성 있는 릴레이 설계(Reliable Relay Design)는 적절한 접점 정격(Contact Rating), 코일 여자, 부하별 디레이팅(Load-Specific Derating), 과도 현상 억제(Transient Suppression), 돌입 전류 관리(Inrush Management), 열 제어(Thermal Control), 환경 보호(Environmental Protection), 퓨즈 협조(Fuse Coordination), 진단(Diagnostics), 검증 시험(Validation Testing)을 통합한다. 수명은 릴레이 자체에 고정된 하나의 숫자가 아니라 장치와 실제 응용 환경의 상호작용 결과이다. 이러한 상호작용을 이해하면 릴레이 시스템에서 예측 가능한 전기적 수명과 신뢰할 수 있는 장기 동작(Long-Term Operation)을 확보할 수 있다.
