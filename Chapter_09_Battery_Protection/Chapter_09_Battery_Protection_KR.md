**Volume 04. Fuse, Relay, and Power Distribution Unit**

# Chapter 09. Battery Protection

## 09.01. Overcurrent Protection

![](images/image1.png){width="7.268055555555556in" height="7.268055555555556in"}

배터리 시스템의 과전류 보호(Overcurrent Protection)는 도체, 셀(Cell), 버스바(Busbar), 접촉기(Contactor), 커넥터(Connector), 하위 전자장치가 과도한 발열이나 영구적인 손상을 유발할 수 있는 전류에 노출되는 것을 방지한다. 일반적인 부하 제어(Load Control)와 달리 보호 기능은 비정상적인 운전 조건에서도 유효하게 동작해야 한다. 따라서 저장된 배터리 에너지와 배전망(Power Distribution Network)에 연결된 전기 부하 사이에서 핵심적인 안전 계층(Safety Layer)을 형성한다.

배터리 과전류(Battery Overcurrent)는 과부하(Overload), 모터 구속(Motor Stall), 인버터 고장(Inverter Failure), 배선 고장(Wiring Fault), 절연 파괴(Insulation Breakdown), 커넥터 손상(Connector Damage), 의도하지 않은 저임피던스 경로(Low-Impedance Path) 등으로 발생할 수 있다. 전류의 크기뿐 아니라 지속시간도 중요하다. 전기 부품에는 열 관성(Thermal Inertia)이 있기 때문에 중간 수준의 과부하는 수 초간 허용될 수 있지만 심각한 고장은 수 밀리초 이내에 차단해야 할 수 있다. 따라서 보호 기능은 단일 고정 임계값이 아니라 전류와 시간을 함께 평가해야 한다.

기본적인 보호 구조(Protection Structure)는 전류 감지(Current Sensing), 판단 로직(Decision Logic), 차단 장치(Interruption Device)를 결합한다. 전류는 션트 저항(Shunt Resistor), 홀 효과 센서(Hall-Effect Sensor), 자기 센서(Magnetic Sensor), 지능형 전력 장치(Intelligent Power Device) 등을 사용하여 측정할 수 있다. 측정값은 아날로그 회로(Analog Circuitry), 배터리 관리 시스템(Battery Management System, BMS), 전자식 보호 제어기(Electronic Protection Controller)에 의해 설정된 보호 한계와 비교된다. 위험 상태가 확인되면 퓨즈(Fuse), 접촉기(Contactor), 회로 차단기(Circuit Breaker), 반도체 스위치(Semiconductor Switch)를 이용하여 해당 전류 경로를 차단한다.

퓨즈(Fuse)는 축적된 열에너지(Thermal Energy)가 설계 한계를 초과하면 퓨즈 소자가 용단되기 때문에 단순하면서도 높은 신뢰성을 갖는 수동 보호(Passive Protection)를 제공한다. 퓨즈 동작은 일반적으로 시간-전류 곡선(Time-Current Curve)과 I²t 관계로 표현되며, 짧은 과도 전류(Transient Current)는 허용하면서 지속적인 과부하나 높은 고장 전류를 차단한다. 배터리 시스템의 퓨즈 선정에서는 연속 전류, 주변 온도, 도체 허용전류, 예상 돌입전류(Inrush Current), 예상 고장전류(Available Fault Current), 정격전압, 차단용량(Interrupting Capacity)을 고려해야 한다.

접촉기(Contactor)는 제어 가능한 절연 및 차단 기능을 제공하며, 비정상 전류가 감지되었을 때 배터리 관리 시스템(BMS)이 배터리를 전기 시스템으로부터 분리할 수 있도록 한다. 그러나 퓨즈와 달리 접촉기는 모든 단락전류(Short-Circuit Current)를 안전하게 차단할 수 있는 것은 아니다. 매우 높은 직류 전류(DC Current)는 심각한 아크(Arc), 접점 침식(Contact Erosion), 접점 용착(Contact Welding)을 발생시킬 수 있다. 따라서 배터리 아키텍처에서는 제어 보호와 절연을 위해 접촉기를 사용하면서 최종적인 수동 보호 장벽으로 적절한 정격의 퓨즈를 함께 사용하는 것이 일반적이다.

전자식 과전류 보호(Electronic Overcurrent Protection)는 여러 전류 임계값과 서로 다른 응답시간을 설정할 수 있다. 비교적 낮은 임계값은 지속적인 과부하를 검출하고, 더 높은 임계값은 신속한 차단이 필요한 심각한 고장을 식별하도록 구성할 수 있다. 필터링(Filtering)과 판정 지연(Qualification Delay)을 적용하면 무해한 스위칭 과도현상이나 모터 가속 전류에 의한 불필요한 트립(Nuisance Trip)을 방지할 수 있다. 이러한 다단계 전략(Multi-Level Strategy)은 단일 순간 전류 한계보다 정상적인 동적 운전과 위험한 전기적 상태를 더욱 효과적으로 구분한다.

보호 임계값(Protection Threshold)은 배터리 셀의 정격만을 기준으로 설정하는 것이 아니라 전체 전류 경로(Current Path)의 안전 운전 한계(Safe Operating Limit)를 기반으로 설정해야 한다. 케이블, 커넥터, 버스바, 인쇄회로기판 배선(PCB Trace), 접촉기, 퓨즈, 컨버터(Converter), 모터 드라이브(Motor Drive)의 허용전류를 모두 고려해야 한다. 특히 주변 또는 인클로저 온도가 상승하면 열적 여유(Thermal Margin)가 감소하므로 온도 디레이팅(Temperature Derating)이 중요하다. 따라서 보호 대상 경로에서 가장 취약한 부품이 전체 분기의 실질적인 연속전류 한계를 결정할 수 있다.

배터리 팩(Battery Pack)과 개별 하위 분기(Downstream Branch)에는 상호 조정된 보호가 필요하다. 메인 배터리 퓨즈(Main Battery Fuse)는 고에너지 전원과 주 배전 경로를 보호하며, 분기 퓨즈(Branch Fuse), 회로 차단기(Circuit Breaker), 전자식 스위치(Electronic Switch)는 더 작은 도체와 부하를 보호한다. 적절한 보호 협조(Protection Coordination)를 적용하면 국부적인 고장이 발생했을 때 가능한 한 전체 로봇을 정지시키지 않고 문제가 발생한 분기만 차단할 수 있다. 이러한 선택적 동작(Selective Operation)은 배터리 방향으로 전파되는 고장에 대한 보호를 유지하면서 시스템 가용성(Availability)을 향상시킨다.

과전류 보호는 정상적으로 발생하는 과도 부하(Transient Load)도 수용해야 한다. 모터, 펌프, 압축기, DC/DC 컨버터(DC/DC Converter), 용량성 입력(Capacitive Input), 컴퓨팅 장치는 기동 시 정상상태 전류보다 상당히 높은 기동전류 또는 돌입전류(Inrush Current)를 발생시킬 수 있다. 보호 장치를 정격 운전전류만을 기준으로 선정하면 불필요한 트립이 발생할 수 있다. 반대로 이러한 과도전류를 허용하기 위해 보호 정격을 지나치게 높이면 배선이 충분히 보호되지 않을 수 있다. 따라서 시간-전류 특성(Time-Current Characteristic)은 두 조건 사이의 핵심적인 공학적 절충점을 제공한다.

회생제동(Regenerative Braking)이나 양방향 전력변환(Bidirectional Power Conversion)을 지원하는 시스템에서는 배터리 전류가 양방향으로 흐를 수 있다. 따라서 보호 로직(Protection Logic)은 허용된 충전 및 회생전류와 비정상적인 역방향 또는 방전전류를 구분해야 한다. 배터리의 충전 한계와 방전 한계가 크게 다를 수 있으므로 양의 전류와 음의 전류에 각각 별도의 임계값을 적용할 수 있다. 방향 인식 전류 감시(Direction-Aware Current Monitoring)는 전류의 절댓값만 사용하는 보호 방식에서 발견하기 어려운 고장도 식별할 수 있도록 한다.

보호 장치의 물리적인 배치(Physical Placement)는 고장 보호 범위(Fault Coverage)에 큰 영향을 준다. 메인 퓨즈는 보호되지 않은 도체의 길이를 최소화할 수 있도록 일반적으로 배터리 에너지원 가까이에 배치해야 한다. 분기 보호 장치는 도체 크기나 허용전류가 변경되는 지점 가까이에 위치해야 한다. 전류 센서는 보호하고자 하는 고장 경로를 충분히 감시해야 하며, 측정 또는 차단 장치를 우회하는 전류가 발생하지 않도록 병렬 도체(Parallel Conductor)나 대체 귀환 경로(Return Path)도 함께 고려해야 한다.

과전류 검출(Overcurrent Detection)은 단순한 비상 차단 기능으로만 동작하는 것이 아니라 시스템 진단(System Diagnostics)과 연계되어야 한다. 제어기는 최대 전류(Peak Current), 고장 지속시간, 해당 채널, 배터리 전압, 온도, 운전 상태, 트립 원인(Trip Reason)을 기록할 수 있다. 이러한 정보는 배선 고장과 반복적인 과부하, 구속된 액추에이터(Stalled Actuator), 열화된 커넥터, 비정상적인 모터 동작을 구분하는 데 도움을 준다. 고장 이벤트 기록(Fault Event Logging)은 정비 진단을 지원하고 심각한 고장으로 발전하기 전에 반복적인 전기적 문제를 식별할 수 있도록 한다.

이동로봇(Mobile Robot)에서는 주행 모터가 높은 과도전류를 요구하는 반면 센서와 컴퓨팅 시스템은 안정적이고 연속적인 전력을 필요로 하므로 보호 협조(Protection Coordination)가 특히 중요하다. 주행 계통의 과부하로 인해 안전 제어기(Safety Controller), 통신 장치, 필수 인지 장비(Perception Equipment)의 전원까지 불필요하게 차단되어서는 안 된다. 고전류 추진 분기(High-Current Propulsion Branch)와 중요 저전력 분기(Critical Low-Power Branch)를 분리하고 보호 장치를 적절히 협조시키면 고장을 격리하면서도 제어된 종료(Controlled Shutdown)와 진단 기능을 유지할 수 있다.

과전류 보호는 하나의 장치에 의존하기보다 다계층 방어(Layered Defense) 구조로 설계해야 한다. 전자식 전류 제한(Electronic Current Limiting)은 빠르게 반응하여 반도체 하드웨어를 보호하고, 배터리 관리 시스템(BMS)은 운전 한계를 초과할 경우 접촉기 개방을 명령할 수 있다. 분기 보호(Branch Protection)는 국부적인 고장을 격리하며, 메인 퓨즈(Main Fuse)는 극단적인 고장전류에 대해 독립적인 보호를 제공한다. 각 계층은 서로 다른 고장 전류 크기와 응답시간 영역을 담당하여 특정 검출 또는 차단 장치 하나에 대한 의존성을 감소시킨다.

검증(Validation)에서는 정상 운전, 과부하, 모터 구속, 돌입전류, 회생전류, 배선 고장, 심각한 단락 조건에 걸쳐 올바른 보호 동작을 입증해야 한다. 시험에는 온도 극한 조건, 최소 및 최대 배터리 전압, 노화된 부품, 실제와 유사한 도체 저항 조건도 포함해야 한다. 트립 임계값(Trip Threshold), 차단시간(Clearing Time), 접촉기 동작, 퓨즈 협조(Fuse Coordination), 고장 후 절연(Post-Fault Isolation)을 함께 검증하여 개별 부품의 정격 만족을 넘어 실제 구현된 시스템이 의도된 보호 계층 구조와 일치하는지 확인해야 한다.

잘 설계된 배터리 과전류 보호 시스템(Battery Overcurrent Protection System)은 안전성(Safety), 가용성(Availability), 과도전류 허용 능력(Transient Tolerance), 고장 격리(Fault Isolation) 사이에서 균형을 확보해야 한다. 목적은 단순히 전류가 높아질 때마다 차단하는 것이 아니라 전류의 크기, 방향, 지속시간, 운전 상황을 종합하여 위험한 상태인지를 판단하는 것이다. 협조된 전류 감지, 지능형 제어, 접촉기, 분기 보호, 수동 퓨즈 보호를 결합하면 자율이동로봇(Autonomous Mobile Robot, AMR), 매니퓰레이터(Manipulator), 이동 플랫폼(Mobile Platform) 및 다양한 배터리 기반 로봇 시스템에 적합한 견고한 보호 아키텍처(Protection Architecture)를 구성할 수 있다.

## 09.02. Overvoltage/Undervoltage Protection

![](images/image2.png){width="7.268055555555556in" height="7.268055555555556in"}

배터리 과전압 및 저전압 보호(Battery Overvoltage and Undervoltage Protection)는 모든 셀(Cell)과 전체 배터리 팩(Battery Pack)이 정의된 전기적 운전 한계(Electrical Operating Limits) 내에서 동작하도록 유지한다. 과도한 전압은 전해질 분해(Electrolyte Decomposition)를 가속하고 발열을 증가시키며 셀 화학 특성을 손상시켜 심각한 안전 위험을 발생시킬 수 있다. 반대로 과도한 방전은 회복할 수 없는 용량 손실이나 내부 열화를 일으킬 수 있다. 따라서 보호 시스템은 전압을 지속적으로 감시하고 안전 운전 영역(Safe Operating Area)을 벗어난 동작을 방지해야 한다.

전압 보호(Voltage Protection)는 셀 수준(Cell-Level)과 팩 수준(Pack-Level)의 상태를 구분해야 한다. 팩 전압(Pack Voltage)은 전체적인 배터리 상태를 나타내지만, 전체 팩 전압이 허용 범위에 있더라도 개별 셀은 위험한 한계에 도달할 수 있다. 제조 편차, 온도 구배(Temperature Gradient), 노화, 불균등한 자기방전(Self-Discharge), 셀 불균형(Cell Imbalance)으로 인해 동일한 직렬 스트링(Series String) 내에서도 셀 전압이 서로 달라질 수 있다. 따라서 신뢰성 있는 보호를 위해서는 팩 수준 측정뿐만 아니라 개별 셀 감시(Individual Cell Monitoring)가 필요하다.

과전압(Overvoltage)은 주로 충전, 회생제동(Regenerative Braking), 충전기 이상 동작 또는 비정상적인 에너지 회수 과정에서 발생한다. 셀이 상한 전압(Upper Voltage Limit)에 접근하면 배터리 관리 시스템(Battery Management System, BMS)은 전기화학적 운전 경계(Electrochemical Operating Boundary)를 초과하기 전에 충전 전류를 감소시키거나 충전을 중단해야 한다. 이동로봇(Mobile Robot)에서는 주행 모터의 회생에너지(Regenerative Energy)도 배터리 전압을 빠르게 상승시킬 수 있으므로 BMS, 모터 제어기(Motor Controller), 인버터(Inverter), 충전기(Charger), 배전 시스템(Power Distribution System) 간의 협조가 필요하다.

저전압(Undervoltage)은 일반적으로 배터리가 과도하게 방전되거나 높은 부하로 인해 일시적인 전압 강하(Voltage Sag)가 발생할 때 나타난다. 보호 시스템은 회복 가능한 일시적 전압 강하와 실제 과방전(Excessive Discharge)을 구분해야 한다. 모터는 가속, 경사로 주행, 조향 또는 구속(Stall) 상태에서 상당한 전류를 요구할 수 있으며, 배터리 내부저항(Internal Resistance) 때문에 단자전압(Terminal Voltage)이 일시적으로 낮아질 수 있다. 따라서 모든 순간적인 전압 저하에 즉시 시스템을 정지시키면 정상적인 로봇 운전 중 불필요한 중단이 발생할 수 있다.

셀 전압 임계값(Cell Voltage Threshold)은 일반적으로 하나의 트립 지점(Trip Point)이 아니라 경고(Warning), 제어(Control), 차단(Shutdown) 영역으로 구성된다. 전압이 한계에 접근하면 시스템은 먼저 경고를 발생시키거나 허용 전력을 감소시킬 수 있다. 전압이 계속 임계 영역으로 진행되면 충전 또는 방전을 제한할 수 있으며, 필요한 경우 최종 보호 임계값(Final Protection Threshold)에서 배터리 절연(Isolation)을 명령한다. 이러한 단계적 대응(Staged Response)은 완전한 전기적 차단 전에 시스템 성능을 제어된 방식으로 저하시킬 수 있도록 한다.

히스테리시스(Hysteresis)는 부하 또는 충전원이 제거된 직후 배터리 전압이 회복될 수 있기 때문에 중요하다. 히스테리시스가 없으면 보호 임계값 근처에서 시스템이 고장 상태와 정상 상태 사이를 반복적으로 전환할 수 있다. 서로 다른 트립 전압(Trip Level)과 복귀 전압(Recovery Level)을 사용하면 이러한 진동을 방지할 수 있다. 또한 시간 판정(Time Qualification)을 적용하여 짧고 무해한 전압 변동은 무시하면서 지속적이거나 심각한 전압 이상은 그 크기와 지속시간에 따라 보호 동작을 시작하도록 구성할 수 있다.

전압 감지 정확도(Voltage Sensing Accuracy)는 보호 여유(Protection Margin)에 직접적인 영향을 미친다. 셀 감시 회로(Cell-Monitoring Circuit), 아날로그 프런트엔드(Analog Front End), 아날로그-디지털 변환기 분해능(ADC Resolution), 기준전압 정확도(Reference Accuracy), 배선 저항, 커넥터 건전성(Connector Integrity), 온도 드리프트(Temperature Drift)는 모두 측정 불확도(Measurement Uncertainty)에 영향을 준다. 따라서 실제 전기화학적 셀 한계와 보호 트립 지점 사이에 충분한 여유를 확보해야 하며, 측정 오류로 인해 셀이 의도된 안전 전압 범위를 벗어나지 않도록 교정(Calibration)과 진단 점검(Diagnostic Check)이 필요하다.

충전 중 과전압 보호(Overvoltage Protection)는 일반적으로 여러 보호 동작을 상호 협조하여 수행해야 한다. 셀이 상한에 접근하면 BMS는 충전 전류 감소를 요청하고, 셀 밸런싱(Cell Balancing)을 수행하여 셀 간 전압 차이를 줄이며, 필요한 경우 충전기의 동작을 중단시킬 수 있다. 통신이나 충전기 제어가 실패하면 독립적인 보호 기능이 충전 접촉기(Charging Contactor)를 개방하거나 배터리를 절연해야 한다. 이러한 다계층 접근(Layered Approach)은 하나의 제어 또는 통신 고장이 과충전 방지를 위한 유일한 보호 장벽을 무력화시키는 것을 방지한다.

셀 밸런싱(Cell Balancing)은 과전압 보호를 지원하지만 이를 대신하는 보호 기능으로 간주해서는 안 된다. 직렬 배터리 팩에서는 가장 높은 전압을 가진 셀이 추가 충전이 가능한 안전 범위를 결정한다. 수동 또는 능동 밸런싱(Passive or Active Balancing)은 셀 간 전압 차이를 줄이고 사용 가능한 팩 용량을 증가시킬 수 있지만, 일반적으로 밸런싱 능력은 추진 또는 충전 전류보다 훨씬 작다. 따라서 보호 로직(Protection Logic)은 평균 팩 전압과 관계없이 실제 최대 셀 전압(Maximum Cell Voltage)에 따라 동작해야 한다.

저전압 보호(Undervoltage Protection) 역시 전체 팩 전압에만 의존하지 않고 가장 낮은 전압을 가진 셀(Lowest-Voltage Cell)을 고려해야 한다. 성능이 저하되거나 열화된 셀은 특히 높은 전류 조건에서 다른 셀보다 먼저 최소 안전전압(Minimum Safe Voltage)에 도달할 수 있다. 팩 전압이 허용된다는 이유만으로 방전을 계속하면 해당 셀이 과도하게 방전될 수 있다. 최소 셀 전압(Minimum Cell Voltage)을 감시하면 BMS가 부하를 줄이고 저에너지 경고(Low-Energy Warning)를 발생시키거나 회복 불가능한 열화가 발생하기 전에 방전 경로를 차단할 수 있다.

배터리 전압은 전류, 온도, 충전상태(State of Charge, SOC), 내부저항(Internal Resistance)에 크게 영향을 받는다. 저온에서는 내부저항이 증가하여 상당한 에너지가 남아 있더라도 부하가 인가될 때 더 큰 전압 강하가 발생할 수 있다. 노화된 배터리도 내부저항 증가로 인해 유사한 특성을 나타낼 수 있다. 따라서 보호 보정(Protection Calibration)은 모든 낮은 단자전압을 완전 방전 상태와 동일하게 판단하지 않도록 설계해야 하며, 동시에 절대로 위반해서는 안 되는 셀의 절대 최소전압 한계(Absolute Cell Voltage Limit)는 유지해야 한다.

로봇 플랫폼(Robotic Platform)에서는 저전압 상태가 발생하기 시작했을 때 즉각적인 정지보다 제어된 전력 감소(Controlled Power Reduction)가 더 적합한 경우가 많다. 상위 제어기(Supervisory Controller)는 가속도를 낮추고, 주행 토크(Traction Torque)를 제한하며, 필수적이지 않은 보조 부하(Auxiliary Load)를 차단하거나 로봇이 충전소(Charging Station)로 복귀하도록 명령할 수 있다. 우선순위 기반 배전(Prioritized Power Distribution)을 통해 핵심 컴퓨팅, 통신, 제동 및 안전 시스템의 전력을 유지할 수 있으며, 완전한 배터리 절연은 지속적인 방전이 배터리 건전성을 위협하는 조건에서 수행한다.

팩 접촉기(Pack Contactor)는 많은 배터리 시스템에서 주요 제어 절연 수단(Controlled Isolation Mechanism)을 제공한다. 심각한 과전압 또는 저전압 상태가 확인되면 BMS는 적절한 접촉기의 개방을 명령하여 추가적인 충전이나 방전을 방지할 수 있다. 그러나 아키텍처 설계에서는 접촉기 고장, 접점 용착(Welded Contact), 보조 전력 경로(Auxiliary Power Path), 충전기 연결, 회생전류 경로(Regenerative Current Path)도 고려해야 한다. 배터리 전압 한계를 위반할 수 있는 모든 전류 경로가 적절히 제어될 때에만 보호 기능이 효과적으로 작동한다.

과전압 및 저전압 진단(Overvoltage and Undervoltage Diagnostics)은 문제가 발생한 셀, 최소 및 최대 셀 전압, 팩 전압, 전류, 온도, 운전 모드(Operating Mode), 고장 지속시간, 보호 동작에 관한 정보를 보존해야 한다. 과거 데이터(Historical Data)를 분석하면 점진적인 셀 불균형, 용량 열화(Capacity Degradation), 비정상적인 충전기 동작, 과도한 회생 이벤트(Regenerative Event), 증가하는 내부저항 등을 파악할 수 있다. 따라서 전압 보호는 즉각적인 안전 메커니즘인 동시에 배터리 건전성(Battery Health)에 관한 중요한 정보원이 된다.

보호 협조(Protection Coordination)는 충전기, DC/DC 컨버터(DC/DC Converter), 인버터, 모터 드라이브(Motor Drive), 스마트 전력분배장치(Smart Power Distribution Unit, Smart PDU), 상위 제어기까지 포함해야 한다. 충전기는 접촉기 절연이 필요해지기 전에 BMS의 전압 제한에 대응해야 하며, 배터리가 추가 에너지를 수용할 수 없는 경우 주행 제어기는 회생전류를 감소시켜야 한다. 저전압 운전 중에는 배터리가 최종 차단 임계값에 도달하기 전에 하위 부하가 전력 제한 명령에 대응해야 한다. 이러한 협조 제어(Coordinated Control)는 갑작스러운 시스템 정지와 불필요한 부품 스트레스를 줄인다.

검증(Validation)은 정상 충전 및 방전, 최대 충전전압, 과방전, 고전류에 의한 전압 강하, 회생제동, 충전기 오동작, 셀 불균형, 저온 운전, 노화된 셀의 동작, 센서 고장, 통신 장애 조건을 포함해야 한다. 임계값 정확도(Threshold Accuracy), 응답 지연(Response Delay), 히스테리시스, 복귀 동작(Recovery Behavior), 접촉기 동작, 경고 기능, 고장 기록(Fault Logging)을 전체 목표 운전 범위에서 검증하여 일시적 및 지속적인 전압 이상 조건 모두에서 보호 기능이 효과적으로 유지되는지 확인해야 한다.

견고한 배터리 전압 보호 아키텍처(Battery Voltage Protection Architecture)는 정확한 셀 및 팩 전압 측정, 단계별 임계값(Staged Threshold), 시간 판정(Time Qualification), 히스테리시스, 셀 밸런싱, 전력 제한(Power Limiting), 충전기 및 모터의 협조 제어, 접촉기 절연, 진단 감시(Diagnostic Monitoring)를 통합한다. 과전압 및 저전압 보호는 단순히 고정된 전압 한계에서 배터리를 차단하는 기능이 아니라, 모든 셀을 안전 운전 영역 내에 유지하면서 에너지 흐름(Energy Flow)을 지능적으로 관리하고 로봇 플랫폼의 가용성(Availability), 신뢰성(Reliability), 안전성(Safety)을 유지하도록 설계되어야 한다.

## 09.03. Reverse-Polarity Protection

![](images/image3.png){width="7.268055555555556in" height="7.268055555555556in"}

역극성 보호(Reverse Polarity Protection)는 양극(Positive)과 음극(Negative) 단자가 잘못 연결되었을 때 배터리 또는 전기 하위 시스템(Electrical Subsystem)이 손상되는 것을 방지한다. 역방향 연결(Reversed Connection)은 반도체 접합부(Semiconductor Junction), 극성 커패시터(Polarized Capacitor), 제어 전자장치(Control Electronics), 모터 드라이브(Motor Drive), 센서(Sensor), 통신 모듈(Communication Module)에 의도하지 않은 방향으로 전류를 흐르게 할 수 있다. 배터리 시스템은 매우 높은 전류를 공급할 수 있으므로 짧은 시간의 극성 오류도 즉각적인 부품 고장, 과열 또는 도체 손상을 발생시킬 수 있다.

역극성 사고(Reverse Polarity Event)는 배터리 교체, 유지보수, 커넥터 조립, 정비 작업(Service Operation), 점프 시동 절차(Jump-Start Procedure), 탈착식 배터리 모듈(Removable Battery Module)의 통합 과정에서 발생할 수 있다. 잘못된 배선이나 손상된 커넥터도 동일한 상태를 발생시킬 수 있다. 로봇 시스템(Robotic System)은 배터리, 페이로드 모듈(Payload Module), 충전기(Charger), 보조 장비(Auxiliary Equipment)를 빈번하게 연결하고 분리할 수 있으므로 기계적 예방(Mechanical Prevention)과 전기적 보호(Electrical Protection)가 모두 필요하다.

첫 번째 보호 계층(Protection Layer)은 일반적으로 커넥터와 와이어 하니스(Wire Harness) 설계를 통한 예방이어야 한다. 극성 커넥터(Polarized Connector), 키 구조 하우징(Keyed Housing), 서로 다른 단자 치수, 기계적 코딩(Mechanical Coding), 명확한 식별 표시, 관리된 조립 절차를 적용하면 역방향 연결 가능성을 줄일 수 있다. 이러한 방법은 전기에너지가 인가되기 전에 고장을 방지하기 때문에 매우 효과적이다. 그러나 예상 가능한 배선, 정비 또는 커넥터 고장에 대비하여 전기적 보호도 함께 적용해야 한다.

단순한 직렬 다이오드(Series Diode)는 가장 기본적인 역극성 보호 방법 중 하나이다. 정상 극성에서는 다이오드가 도통하여 부하에 전원을 공급하고, 극성이 반대로 연결되면 전류 흐름을 차단한다. 이 방식은 저렴하고 구조적으로 단순하지만 순방향 전압강하(Forward Voltage Drop)로 인해 지속적인 전력 손실과 발열이 발생한다. 높은 배터리 전류에서는 이러한 손실이 허용하기 어려운 수준이 될 수 있으므로 일반적인 다이오드 보호는 추진 전력 경로보다는 저전력 제어 및 보조 회로에 더 적합하다.

쇼트키 다이오드(Schottky Diode)는 일반적인 실리콘 다이오드(Silicon Diode)에 비해 순방향 전압강하를 낮출 수 있으므로 도통 손실(Conduction Loss)을 감소시킬 수 있다. 그러나 높은 전류에서는 여전히 상당한 전력 손실이 발생할 수 있으며, 역전압 허용 능력(Reverse-Voltage Capability), 누설전류(Leakage Current), 접합부 온도(Junction Temperature), 열 관리(Thermal Management)를 고려해야 한다. 에너지 효율과 운전시간이 중요한 배터리 기반 로봇에서는 반도체의 도통 손실이 직접적으로 사용 가능한 운전시간을 감소시키고 냉각 요구사항을 증가시킨다.

MOSFET 기반 역극성 보호(MOSFET-Based Reverse Polarity Protection)는 도통 손실을 크게 줄일 수 있으며 전자식 배터리 인터페이스(Electronic Battery Interface)에 널리 적용할 수 있다. 적절하게 구성된 MOSFET은 정상 연결 상태에서 채널(Channel)을 저저항 전류 경로로 사용하고 배터리 극성이 반대로 연결되면 전류를 차단한다. 도통 손실은 대략 전류의 제곱과 온상태 저항(On-State Resistance)에 비례하므로 충분히 낮은 RDS(on)을 가진 소자를 선정하면 직렬 다이오드보다 훨씬 높은 효율을 얻을 수 있다.

MOSFET의 내부 바디 다이오드(Intrinsic Body Diode)는 MOSFET이 완전히 턴온(Turn-On)되기 전의 전류 흐름을 결정하므로 신중하게 고려해야 한다. 따라서 소자의 방향은 일반적인 스위칭 응용에서 직관적으로 예상하는 방향과 다를 수 있다. 게이트 제어 회로(Gate-Control Circuit)는 정상 배터리 극성에서는 MOSFET을 턴온시키고 역극성에서는 턴오프(Turn-Off) 상태를 유지하도록 설계해야 하며, 최대 배터리 전압이나 과도 상태(Transient Condition)에서도 허용 가능한 게이트-소스 전압(Gate-to-Source Voltage)을 초과해서는 안 된다.

고전류 배터리 시스템에서는 유효 저항(Effective Resistance)을 감소시키고 열 부하(Thermal Loading)를 분산하기 위해 여러 MOSFET을 병렬로 연결할 수 있다. 이 경우 전류 분배(Current Sharing), 게이트 저항(Gate Resistance), 인쇄회로기판 구리 면적(PCB Copper Area), 버스바(Busbar) 설계, 열 인터페이스(Thermal Interface), 소자 파라미터 편차(Device Parameter Variation)를 고려해야 한다. 단순히 병렬 소자의 수를 늘린다고 균등한 전류 분배가 보장되는 것은 아니며, 특히 스위칭 과도 상태에서는 전기적 및 열적 대칭성(Electrical and Thermal Symmetry)을 물리적 설계에 반영해야 한다.

백투백 MOSFET(Back-to-Back MOSFET) 구성은 응용 시스템에서 양방향 절연이 필요한 경우 양방향 전류 차단(Bidirectional Current Blocking)을 제공할 수 있다. 이는 충전, 회생제동(Regenerative Braking), 외부 전원(External Power Source)으로 인해 전류가 배터리에서 외부로뿐만 아니라 배터리 방향으로도 흐를 수 있는 시스템에 유용하다. 서로 반대 방향의 바디 다이오드를 갖도록 두 MOSFET을 제어하면 의도된 양방향 동작을 허용하면서 보호 명령이 발생했을 때 원하지 않는 전류를 차단할 수 있다.

고전류 로봇 배터리 시스템(High-Current Robotic Battery System)에서는 역극성 보호 전략의 일부로 접촉기(Contactor)를 사용할 수 있다. 메인 접촉기(Main Contactor)를 닫기 전에 제어기는 보호된 감지 경로(Protected Sensing Path)를 이용하여 배터리 극성과 전압을 확인할 수 있다. 측정된 극성이 잘못된 경우 접촉기는 개방 상태를 유지하고 메인 전력 버스(Main Power Bus)는 활성화되지 않는다. 이러한 방식은 추진 시스템의 동작 전류가 단순한 직렬 반도체 보호로 처리하기에는 지나치게 높은 경우 특히 유용하다.

극성 검출 회로(Polarity Detection Circuitry)는 자신이 검출해야 하는 고장 조건 자체를 견딜 수 있어야 한다. 전압 분배기(Voltage Divider), 비교기(Comparator), 절연 측정 회로(Isolated Measurement Circuit), 아날로그-디지털 변환기 입력(ADC Input), 보호 부품은 역방향 배터리 전압이 인가되어도 감시 전자장치가 손상되지 않도록 설계해야 한다. 감지 회로는 하위 전력단(Downstream Power Stage)에 전원을 인가하기 전에 정상 극성, 역극성, 배터리 분리 또는 비정상 전압 상태를 BMS나 상위 제어기(Supervisory Controller)에 전달할 수 있다.

역극성 보호는 독립적인 기능으로 취급하기보다 퓨즈(Fuse) 및 과전류 보호(Overcurrent Protection)와 협조되어야 한다. 일부 보호 구성은 역방향 연결 시 의도적으로 저임피던스 경로(Low-Impedance Path)를 형성하여 퓨즈가 개방되도록 하며, 다른 방식은 전자적으로 역방향 전류를 차단한다. 퓨즈 기반 전략에서는 발생하는 고장전류가 예측 가능해야 하며 배선이나 부품이 손상되기 전에 퓨즈가 차단되어야 한다. 이러한 고장이 발생한 이후 필요한 정비 작업도 함께 고려해야 한다.

보호 장치(Protection Device)는 최대 배터리 전압, 예상 전류, 역전압(Reverse Voltage), 서지 조건(Surge Condition), 열적 환경에 적합한 정격을 가져야 한다. MOSFET의 드레인-소스 전압 정격(Drain-Source Voltage Rating)은 스위칭 과도현상, 케이블 인덕턴스(Cable Inductance), 부하 변동(Load Disturbance)을 고려하여 충분한 여유를 확보해야 한다. 연속전류 허용 능력만으로는 충분하지 않으며, 과도 에너지(Transient Energy)와 안전 동작 영역(Safe Operating Area, SOA)이 비정상 조건에서 소자의 생존 여부를 결정할 수 있다. 설계 여유를 설정할 때에는 온도 디레이팅(Temperature Derating)도 포함해야 한다.

로봇 전력 아키텍처(Robotic Power Architecture)는 일반적으로 메인 주행 배터리(Main Traction Battery), DC/DC 컨버터 출력(DC/DC Converter Output), 컴퓨팅 전원 레일(Computing Rail), 센서 전원(Sensor Supply), 보조 인터페이스(Auxiliary Interface) 등 여러 전압 영역(Voltage Domain)을 포함한다. 따라서 역극성 보호는 하나 이상의 경계에 적용해야 할 수 있다. 보호된 메인 배터리 연결이 잘못 배선될 수 있는 보조 커넥터까지 자동으로 보호하는 것은 아니다. 외부에서 접근하거나 정비할 수 있는 각각의 전원 인터페이스는 자체적인 고장 노출 조건(Fault Exposure)에 따라 평가해야 한다.

진단 기능(Diagnostics)은 역극성을 저전압(Undervoltage), 개방회로(Open Circuit), 퓨즈 고장(Fuse Failure), 통신 고장(Communication Fault)과 구분함으로써 유지보수성을 향상시킬 수 있다. 제어기는 측정된 입력전압, 검출된 극성, 접촉기 상태, 보호 장치 상태, 발생 시간, 영향을 받은 인터페이스에 관한 정보를 기록할 수 있다. 명확한 진단 정보는 반복적인 잘못된 연결 시도를 방지하고 정비 담당자가 정상적인 배터리나 전자 모듈을 불필요하게 교체하지 않고도 잘못된 배선이나 손상된 커넥터를 식별하도록 지원한다.

보호 아키텍처는 역극성 사고 이후의 복구 동작(Recovery Behavior)도 정의해야 한다. 저에너지 인터페이스에서는 정상 극성이 복원된 후 자동 재연결(Automatic Reconnection)을 허용할 수 있지만, 고에너지 배터리 시스템에서는 의도적인 리셋(Deliberate Reset)이나 진단 확인(Diagnostic Confirmation)이 필요할 수 있다. 해결되지 않은 배선 고장 상태에서 접촉기가 반복적으로 닫히도록 시도해서는 안 된다. 제어된 복구(Controlled Recovery)는 즉각적인 고장이 제거된 이후 반복적인 전기적 또는 기계적 스트레스가 발생하는 것을 방지한다.

검증(Validation)은 정상 연결, 역방향 연결, 입력 개방, 최소 및 최대 배터리 전압, 핫플러그(Hot-Plug) 상황, 부분적으로 체결된 커넥터(Partially Engaged Connector), 과도 교란(Transient Disturbance), 대표적인 부하 조건을 포함해야 한다. 시험을 통해 하위 전자장치가 보호되고, 보호 장치가 열적 및 전기적 한계 내에서 동작하며, 역극성 상태에서는 접촉기가 닫히지 않고, 정상 배터리 연결이 복원된 이후 시스템이 올바르게 복구되는지 확인해야 한다.

견고한 역극성 보호 설계(Robust Reverse Polarity Protection Design)는 기계적 예방(Mechanical Prevention), 보호된 극성 검출(Protected Polarity Detection), 반도체 또는 접촉기 기반 절연(Semiconductor or Contactor-Based Isolation), 적절한 과전류 보호, 진단, 제어된 복구를 결합한다. 구체적인 구현 방식은 전압, 전류, 효율, 양방향 에너지 흐름(Bidirectional Energy Flow), 정비 요구사항(Service Requirements)에 따라 결정된다. 배터리 기반 로봇 플랫폼에서는 단순한 연결 오류가 배터리, 배전 시스템(Power Distribution System), 컴퓨팅 하드웨어, 센서 또는 추진 전자장치(Propulsion Electronics)의 손상으로 확산되지 않도록 하는 것이 핵심 목적이다.

## 09.04. Short-Circuit Protection

![](images/image4.png){width="7.268055555555556in" height="7.268055555555556in"}

단락(Short Circuit)은 서로 다른 전위를 가진 도체 사이에 의도하지 않은 매우 낮은 임피던스 경로(Very-Low-Impedance Path)가 형성되기 때문에 배터리 기반 시스템에서 가장 심각한 전기적 고장 중 하나이다. 이때 발생하는 전류는 수 밀리초 이내에 정상 운전 수준을 크게 초과할 수 있으며, 주로 셀 내부저항(Cell Internal Resistance), 버스바(Busbar) 및 케이블 임피던스, 커넥터 저항, 고장 경로 임피던스(Fault-Path Impedance)에 의해 제한된다. 보호 시스템은 도체, 셀 또는 스위칭 장치가 손상되기 전에 이러한 에너지를 차단해야 한다.

단락은 배터리 양극과 음극 단자 사이, 와이어 하니스(Wire Harness) 내부의 도체 사이, 손상된 커넥터 양단, 전력전자 모듈(Power Electronic Module) 내부 또는 전도성 오염물(Conductive Contamination)을 통해 발생할 수 있다. 기계적 마모, 압착된 케이블, 느슨해진 체결부품, 절연 파괴(Insulation Breakdown), 수분 침투(Water Ingress), 제조 결함, 정비 오류 등이 모두 고장 경로를 형성할 수 있다. 로봇 플랫폼에서는 진동, 반복적인 움직임, 충격, 환경 노출이 추가되므로 전체 사용 수명 동안 이러한 위험이 증가할 수 있다.

예상 단락전류(Available Short-Circuit Current)는 배터리 화학 특성, 충전상태(State of Charge, SOC), 온도, 팩 구성(Pack Configuration), 전체 회로 임피던스에 크게 영향을 받는다. 대규모 병렬 셀 그룹(Parallel Cell Group)은 개별 셀의 전류가 팩 단자에서 합쳐지기 때문에 매우 높은 고장전류를 공급할 수 있다. 따라서 보호 시스템은 정상 연속전류만을 기준으로 설계할 수 없다. 최대 예상 고장전류(Maximum Prospective Fault Current)를 산정하여 모든 차단 장치가 예상되는 전기에너지를 안전하게 견디고 차단할 수 있도록 해야 한다.

배터리 단락 보호(Battery Short-Circuit Protection)는 일반적으로 서로 다른 응답 특성을 갖는 여러 보호 계층(Protection Layer)을 사용한다. 셀 수준 보호 소자(Cell-Level Protective Element)는 극심한 내부 또는 국부 고장을 제한하고, 팩 퓨즈(Pack Fuse)는 주 에너지 경로를 보호한다. 접촉기(Contactor)는 제어 가능한 절연을 제공하며 전자식 스위치(Electronic Switch)나 모터 드라이브(Motor Drive)는 감지된 비정상 전류에 빠르게 대응할 수 있다. 배터리 관리 시스템(Battery Management System, BMS)은 이러한 장치를 감독하고 차단을 협조하지만, 전자 제어가 충분히 빠르게 반응하지 못하는 경우를 대비하여 독립적인 수동 보호(Passive Protection)도 중요하다.

메인 배터리 퓨즈(Main Battery Fuse)는 소프트웨어, 통신 및 제어기 전원과 독립적으로 동작하기 때문에 기본적인 최종 보호 장치(Final Protection Element)이다. 퓨즈의 전류 정격은 정상 연속 부하와 정상적인 과도전류를 허용해야 하며, 시간-전류 특성(Time-Current Characteristic)은 보호 대상 도체가 열적 내량(Thermal Withstand Capability)을 초과하기 전에 심각한 고장을 차단할 수 있어야 한다. 또한 퓨즈의 전압 정격과 차단용량(Interrupting Capacity)은 고에너지 배터리 회로가 개방될 때 발생하는 직류 아크(DC Arc)를 안전하게 소호할 수 있을 만큼 충분해야 한다.

단락 보호를 위한 퓨즈 선정에서는 일반적으로 통과 에너지(Let-Through Energy)라고 불리는 I²t를 고려해야 한다. 고장이 발생하면 퓨즈가 완전히 차단될 때까지 전류가 흐르면서 도체와 하위 부품이 에너지를 흡수한다. 따라서 퓨즈의 차단 특성(Clearing Characteristic)은 케이블, 버스바, 접촉기, 커넥터 및 반도체 소자의 열적·전기적 내량과 적합해야 한다. 단순히 정상 운전전류보다 약간 높은 정격의 퓨즈를 선택하는 것만으로는 적절한 고장 보호를 보장할 수 없다.

전자식 단락 검출(Electronic Short-Circuit Detection)은 열 보호(Thermal Protection)만 사용하는 것보다 훨씬 빠르고 설정 가능한 응답을 제공할 수 있다. 전류 센서(Current Sensor), 션트 측정(Shunt Measurement), 홀 효과 센서(Hall-Effect Sensor), 디새추레이션 검출(Desaturation Detection), 반도체 전류 감지 기능을 이용하여 빠르게 증가하는 고장전류를 식별할 수 있다. 이후 제어기는 전력단(Power Stage)을 비활성화하거나 절연을 명령할 수 있다. 검출은 충분히 빨라야 하지만 실제 단락을 모터 기동, 인버터 스위칭, 용량성 돌입전류(Capacitive Inrush)와 구분하기 위한 필터링도 필요하다.

과부하와 단락 고장은 매우 다른 시간 영역에서 발생하기 때문에 다중 보호 임계값(Multiple Protection Thresholds)이 유용하다. 중간 수준의 과부하는 일시적으로 허용하고 지연 보호(Delayed Protection)로 처리할 수 있지만, 극단적으로 높은 전류는 순간 또는 준순간 보호(Instantaneous or Near-Instantaneous Protection)를 작동시켜야 한다. 이러한 시간-전류 판별(Time-Current Discrimination)을 통해 주행 모터와 컨버터가 정상적인 과도상태를 견디면서도 심각한 고장에 대한 보호를 유지할 수 있다. 임계값은 실제 부품의 내량 한계(Component Withstand Limit)와 협조되어야 한다.

접촉기(Contactor)가 무제한적인 단락 차단 능력을 제공한다고 가정해서는 안 된다. 매우 높은 직류 고장전류 상태에서 접촉기를 개방하면 강력한 아크가 발생하여 접점이 손상되거나 성공적인 차단 자체가 불가능해질 수 있다. 일부 아키텍처에서는 가장 높은 고장전류를 퓨즈가 차단하고 접촉기는 상대적으로 낮은 에너지의 제어된 차단(Controlled Disconnection)을 담당한다. 따라서 접촉기의 투입 능력(Making Capability), 통전 능력(Carrying Capability), 차단 능력(Breaking Capability)을 예상되는 고장 조건에 대해 각각 평가해야 한다.

고에너지 배터리 시스템(High-Energy Battery System)에서는 기존 접촉기가 최대 고장전류를 안전하게 차단하기 어려운 경우 파이로테크닉 차단 장치(Pyrotechnic Disconnect Device) 또는 기타 초고속 절연 기술(Ultra-Fast Isolation Technology)을 고려할 수 있다. 이러한 장치는 트리거 신호를 받은 후 전기 경로를 빠르게 물리적으로 분리할 수 있다. 일반적으로 일회용 장치이므로 작동 후 교체가 필요하지만, 높은 요구 성능이 필요한 시스템에서 전자식 검출과 기존 퓨즈 차단 사이에 추가적인 보호 계층을 제공할 수 있다.

보호 장치의 배치(Protection Placement)는 전기 시스템에서 보호되지 않은 영역의 크기를 결정한다. 메인 퓨즈는 출력 케이블을 따라 발생하는 단락이 보호 장치를 우회하지 않도록 일반적으로 배터리 전원에 가능한 한 가깝게 배치해야 한다. 메인 배전 경로(Main Distribution Path)보다 도체 크기나 허용전류가 작은 각 분기에는 별도의 분기 보호(Branch Protection)가 필요할 수 있다. 보호 장치는 전체 배전 아키텍처에서 도체 허용 능력이 변경되는 지점을 따라 배치되어야 한다.

지락(Ground Fault)과 섀시 관련 단락(Chassis-Related Short Circuit)은 전류 경로가 양극과 음극 사이의 직접 단락과 다를 수 있으므로 추가적인 고려가 필요하다. 접지 아키텍처(Grounding Architecture)와 전기적 절연 상태에 따라 첫 번째 절연 고장은 매우 작은 전류만 발생시킬 수 있지만 두 번째 고장이 발생하면 위험한 저임피던스 경로가 형성될 수 있다. 따라서 배터리 보호는 절연 감시(Insulation Monitoring), 접지 전략, 인클로저 설계(Enclosure Design), 고장 검출과 협조하여 간접적인 단락 조건도 식별할 수 있어야 한다.

단락 보호는 배터리 외부에 저장된 에너지도 고려해야 한다. 인버터, 모터 드라이브, DC/DC 컨버터(DC/DC Converter) 및 기타 전력전자장치의 DC 링크 커패시터(DC-Link Capacitor)는 배터리 접촉기가 개방되기 시작한 이후에도 고장 지점으로 빠르게 방전될 수 있다. 또한 모터는 회생 운전(Regenerative Operation) 중 일시적으로 전기에너지를 공급할 수 있다. 따라서 전체 고장에너지 분석(Fault-Energy Analysis)은 배터리가 유일한 에너지원이라고 가정하지 말고 분산된 용량성 및 전기기계적 에너지(Electromechanical Energy)를 포함해야 한다.

다수의 전기 분기를 포함하는 로봇 시스템에서는 선택적 보호 협조(Selective Coordination)가 중요하다. 보조 센서 회로(Auxiliary Sensor Circuit)에서 단락이 발생한 경우 이상적으로는 해당 로컬 퓨즈(Local Fuse)나 전자식 스위치만 차단되고 로봇 전체의 주행, 안전 제어, 컴퓨팅 전원은 유지되어야 한다. 반대로 메인 버스(Main Bus)의 고장은 신속한 팩 수준 절연(Pack-Level Isolation)이 필요하다. 분기 보호와 메인 보호를 협조하면 국부적인 고장이 전체 전기 아키텍처로 확산되는 것을 방지하면서 시스템 가용성(Availability)을 향상시킬 수 있다.

단락 진단(Short-Circuit Diagnostics)은 측정된 최대 전류(Peak Current), 고장 위치 또는 영향을 받은 분기, 배터리 전압, 온도, 운전 상태, 작동한 보호 장치, 접촉기 상태를 기록해야 한다. 고해상도 이벤트 정보(High-Resolution Event Information)를 활용하면 실제 직접 단락(Hard Short)을 모터 구속(Motor Stall), 인버터 고장, 간헐적인 하니스 손상, 커넥터 오염과 구분하는 데 도움이 된다. 반복적으로 발생하는 과도 고장 기록을 분석하면 영구적인 단락으로 발전하기 전에 배선 열화를 발견할 수도 있다.

단락 사고 이후의 복구(Recovery)는 신중하게 제어되어야 한다. 지속적인 단락 상태에서 접촉기를 자동으로 재투입하면 배터리와 스위칭 장치가 파괴적인 전류에 반복적으로 노출될 수 있다. 고에너지 고장은 일반적으로 진단 조건을 통해 고장이 제거되었음을 확인하거나 정비 작업이 수행될 때까지 보호 상태를 래치(Latch)해야 한다. 저에너지 보호 분기의 경우에도 반복적인 전원 인가가 안전하다는 것을 아키텍처 차원에서 보장할 수 있을 때에만 제어된 재시도(Controlled Retry)를 허용해야 한다.

검증(Validation)은 메인 버스 고장, 분기 고장, 하위 전자장치 고장, 배터리 단자 근처의 고장을 포함하여 대표적인 위치와 임피던스에서 단락을 시험해야 한다. 시험을 통해 검출시간(Detection Time), 최대 전류, 퓨즈 차단 동작(Fuse Clearing Behavior), 접촉기 응답, 도체 온도, 아크 억제(Arc Containment), 진단 기록, 고장 후 절연(Post-Fault Isolation)을 확인해야 한다. 또한 최소 및 최대 배터리 전압, 극한 온도, 부품 공차(Component Tolerance), 노화된 시스템 조건도 고려해야 한다.

견고한 단락 보호 아키텍처(Robust Short-Circuit Protection Architecture)는 고장 예방(Fault Prevention), 저임피던스 전류 경로 분석(Low-Impedance Current-Path Analysis), 적절한 정격의 퓨즈, 신속한 전자식 검출, 협조된 접촉기 동작, 분기 보호, 진단, 제어된 복구를 결합한다. 그 목적은 단순히 과도한 전류를 검출하는 것이 아니라 손상이 확산되기 전에 최대 전류(Peak Current)와 전체 방출 에너지(Total Released Energy)를 제한하는 것이다. 이러한 다계층 전략(Layered Strategy)은 가장 큰 에너지를 수반하는 전기적 고장 모드 중 하나인 단락으로부터 배터리, 배선, 전력전자장치 및 핵심 로봇 시스템을 보호한다.

## 09.05. BMS-Coordinated Protection

![](images/image5.png){width="7.268055555555556in" height="7.268055555555556in"}

BMS 협조 보호(BMS-Coordinated Protection)는 배터리 감지(Battery Sensing), 고장 평가(Fault Evaluation), 전력 제어(Power Control), 물리적 절연(Physical Isolation)을 하나의 통합된 보호 전략으로 구성한다. 과전류, 과전압, 저전압, 역극성, 단락 보호를 각각 독립적인 기능으로 취급하는 대신 배터리 관리 시스템(Battery Management System, BMS)은 배터리 상태, 고장 심각도, 운전 상태 및 연결된 보호 장치의 성능을 기반으로 각각의 보호 동작을 협조한다.

BMS는 개별 셀 전압(Individual Cell Voltage), 팩 전압(Pack Voltage), 충전 및 방전 전류, 셀 및 모듈 온도, 충전상태(State of Charge, SOC), 관련 진단 신호(Diagnostic Signal)를 지속적으로 감시한다. 이러한 측정값은 실시간으로 배터리의 전기적 및 열적 상태를 파악하는 기반이 된다. 따라서 보호 판단은 하나의 임계값만을 기준으로 하지 않고 측정값, 운전 한계, 지속시간, 에너지 흐름 방향(Direction of Energy Flow), 시스템 상태 사이의 관계를 종합하여 수행한다.

보호 한계(Protection Limit)는 일반적으로 여러 단계의 대응 수준(Response Level)으로 구성된다. 운전 경계에 접근하는 상태에서는 먼저 경고(Warning)를 발생시킬 수 있으며, 이상 정도가 증가하면 전류 또는 전력 디레이팅(Power Derating)을 수행할 수 있다. 상태가 계속 악화되면 제어된 종료(Controlled Shutdown)를 수행하고, 심각한 고장에서는 즉각적인 절연(Immediate Isolation)이 필요할 수 있다. 이러한 단계적 전략(Staged Strategy)은 안전한 운전이 가능한 경우 모든 비정상 측정에 대해 배터리를 즉시 차단하지 않고 시스템 가용성(System Availability)을 유지할 수 있도록 한다.

과전류 협조(Overcurrent Coordination)는 이러한 계층적 동작을 명확하게 보여준다. 중간 수준의 과부하는 토크 감소(Torque Reduction), 컨버터 전류 제한(Converter Current Limiting), 부하 차단(Load Shedding)을 통해 처리할 수 있으며, 더 높은 전류 임계값에서는 접촉기(Contactor) 개방을 명령할 수 있다. 매우 높은 단락전류(Short-Circuit Current)는 BMS 소프트웨어와 독립적으로 메인 퓨즈(Main Fuse)가 차단할 수 있다. 따라서 전자식 검출, 제어 가능한 절연, 수동 보호(Passive Protection)는 동일한 기능을 중복하는 것이 아니라 서로 다른 전류 및 시간 영역에서 동작한다.

전압 보호(Voltage Protection)는 셀 수준과 팩 수준 모두에서 협조된다. 충전 중에는 가장 높은 전압의 셀이 상한에 접근함에 따라 BMS가 충전 전류 감소를 요청할 수 있으며, 셀 밸런싱(Cell Balancing)을 통해 셀 간 편차를 줄일 수 있다. 방전 중에는 가장 낮은 셀 전압이 최종 저전압 임계값(Undervoltage Threshold)에 도달하기 전에 전력 감소를 시작할 수 있다. 지속적인 충전이나 방전으로 특정 셀이 허용 운전 영역을 벗어날 가능성이 있는 경우 팩 수준의 접촉기 절연(Pack-Level Contactor Isolation)을 수행한다.

온도(Temperature)는 전기적 한계가 열적 상태에 크게 의존하기 때문에 협조 보호에서 핵심적인 입력값이다. 셀이나 커넥터 온도가 높은 경우 전압과 전류가 정상 범위에 있더라도 충전 또는 방전 전류를 감소시켜야 할 수 있다. 저온에서는 충전이 제한될 수 있으며 부하가 인가될 때 전압 강하(Voltage Sag)가 증가할 수 있다. 따라서 BMS는 전체 환경 운전 범위에서 전기적 임계값을 고정값으로 사용하는 대신 온도 의존형 한계(Temperature-Dependent Limit)를 적용할 수 있다.

BMS는 정상적인 충전 종료 방법으로 접촉기를 개방하는 데 의존하기보다 충전기(Charger)와 협조해야 한다. 먼저 명령 인터페이스(Command Interface)를 통해 충전 전류를 감소시키고 필요한 경우 충전기를 제어된 방식으로 정지시킬 수 있다. 충전기가 명령에 응답하지 않거나 통신이 손실되면 BMS는 보호 단계를 상향하여 충전 경로를 절연할 수 있다. 이를 통해 협조 제어(Cooperative Control)에서 독립적인 물리적 차단(Independent Physical Disconnection)으로 이어지는 보호 계층 구조를 구성한다.

인버터(Inverter) 및 모터 드라이브(Motor Drive)와도 유사한 협조가 필요하다. 가속 중에는 BMS가 배터리 상태에 따라 허용 가능한 최대 방전 전류 또는 전력을 전달할 수 있다. 회생제동(Regenerative Braking) 중에는 허용 가능한 최대 충전 전력을 전달할 수 있다. 배터리가 과전압, 과열 또는 높은 충전상태 한계에 접근하면 BMS가 배터리 접촉기를 개방해야 하는 상황이 발생하기 전에 회생에너지(Regenerative Energy)를 감소시키거나 다른 방식으로 처리해야 한다.

스마트 전력분배장치(Smart Power Distribution Unit, Smart PDU)와 DC/DC 컨버터(DC/DC Converter)는 협조 보호를 하위 분기(Downstream Branch)까지 확장한다. 배터리의 전력 공급 능력이 제한되면 비필수 보조 부하(Nonessential Auxiliary Load)를 감소시키거나 차단하면서 안전 제어기, 통신, 제동, 센싱 및 필수 컴퓨팅에 필요한 전력을 유지할 수 있다. 국부적인 분기 고장(Local Branch Fault)은 전체 배터리 전원을 불필요하게 제거하지 않고 해당 분기만 절연할 수 있다. 이러한 선택적 대응(Selective Response)은 고장 격리와 로봇 시스템 가용성을 모두 향상시킨다.

접촉기 제어(Contactor Control)는 BMS의 가장 중요한 물리적 보호 기능 중 하나이다. 메인 접촉기를 닫기 전에 BMS는 배터리 전압, 극성(Polarity), 절연 상태(Insulation Condition), 접촉기 상태 및 기타 허가 조건(Permissive Condition)을 확인할 수 있다. 이후 프리차지 시퀀스(Pre-Charge Sequence)를 수행하여 하위 DC 링크 커패시턴스(DC-Link Capacitance)가 충전되는 동안 전류를 제한할 수 있다. 허용 가능한 프리차지 동작이 확인된 이후에만 메인 전력 경로를 로봇 전기 시스템에 완전히 연결해야 한다.

운전 중 접촉기 개방 역시 전류와 시스템 상태에 맞추어 협조되어야 한다. 높은 직류 전류를 차단하면 상당한 아크(Arc)와 접점 손상이 발생할 수 있으므로 고장 상황에서 충분한 대응시간이 허용되는 경우 접촉기를 개방하기 전에 제어 가능한 부하를 먼저 감소시켜야 한다. 즉각적인 절연이 필요한 심각한 고장에서는 각 장치의 실제 차단 능력(Interruption Capability)에 따라 접촉기, 퓨즈, 전자식 스위치(Electronic Switch) 또는 기타 차단 장치를 활용하도록 보호 아키텍처를 구성해야 한다.

협조 보호 아키텍처(Coordinated Protection Architecture)는 통신이 실패한 경우에도 효과적인 보호 기능을 유지해야 한다. CAN, CAN FD 또는 기타 통신 링크를 통해 BMS, 충전기, 인버터, PDU, 상위 제어기(Supervisory Controller) 사이에서 배터리 한계와 보호 명령을 전달할 수 있지만 통신 자체가 유일한 안전 장벽(Safety Barrier)이 되어서는 안 된다. 유효한 BMS 정보를 사용할 수 없을 때 타임아웃 동작(Timeout Behavior)과 로컬 폴백 한계(Local Fallback Limit)를 통해 각 하위 시스템이 정의된 안전 상태(Safe State)로 전환되어야 한다.

고장 분류(Fault Classification)는 적절한 보호 대응을 결정하는 데 도움이 된다. 모터 가속 중 발생하는 일시적인 전압 강하는 지속적인 저전압과 반드시 동일하게 처리할 필요가 없으며, 중간 수준의 과부하도 직접 단락(Hard Short Circuit)과 동일한 대응을 적용해서는 안 된다. BMS는 크기, 지속시간, 변화율(Rate of Change), 온도, 전류 방향, 운전 모드를 결합하여 경고 상태, 복구 가능한 고장(Recoverable Fault), 래치 고장(Latched Fault), 즉각적이고 비가역적인 보호가 필요한 고장을 구분할 수 있다.

배터리 에너지(Battery Energy)가 증가할수록 중복성(Redundancy)과 독립성(Independence)은 더욱 중요해진다. BMS는 지능형 감독(Intelligent Supervision)을 제공하지만 소프트웨어 제어 시스템 하나가 모든 위험한 전기적 상태에 대한 유일한 보호 장벽이 되어서는 안 된다. 메인 퓨즈, 하드웨어 과전압 또는 과전류 보호, 독립적인 감지 경로(Independent Sensing Path), 접촉기 피드백(Contactor Feedback) 및 기타 보호 메커니즘이 추가적인 보호 계층을 제공할 수 있다. 각각의 임계값과 응답시간은 BMS 제어 동작과 충돌하지 않고 상호 보완되도록 설계해야 한다.

진단(Diagnostics)은 이벤트의 발생 순서를 통해 실제 고장 메커니즘을 파악할 수 있기 때문에 협조 보호에서 필수적인 요소이다. BMS는 셀 전압, 팩 전압, 전류, 온도, 충전상태, 접촉기 명령, 접촉기 피드백, 충전기 또는 인버터 상태, 활성 전력 한계(Active Power Limit), 고장 타임스탬프(Fault Timestamp)를 기록할 수 있다. 이벤트 이력(Event History)은 배터리 열화를 배선 고장, 충전기 오동작, 모터 과부하, 접촉기 용착(Contact Welding), 비정상적인 운전 명령과 구분하는 데 도움을 준다.

복구 전략(Recovery Strategy)은 고장의 심각도와 안전한 상태가 복원되었다는 확신 수준에 따라 결정되어야 한다. 일시적인 디레이팅은 온도나 전압이 허용 범위로 복귀하면 자동으로 해제될 수 있지만 일부 고장은 제어된 전원 재인가(Controlled Power Cycle)가 필요할 수 있다. 심각한 단락, 접촉기 용착, 절연 고장 또는 반복적인 보호 이벤트는 래치 셧다운(Latched Shutdown)과 정비 점검(Service Inspection)이 필요할 수 있다. 자동 재연결(Automatic Reconnection)은 해결되지 않은 위험한 고장에 반복적으로 전원을 인가해서는 안 된다.

BMS 협조 보호의 검증(Validation)은 개별 보호 기능만 시험하는 것이 아니라 보호 기능 사이의 상호작용을 시험해야 한다. 충전, 고전류 방전, 회생제동, 과부하, 단락, 셀 불균형, 과열, 저온, 통신 손실, 센서 고장, 접촉기 고장을 시스템 수준 시나리오(System-Level Scenario)로 평가해야 한다. 시험에서는 모든 관련 보호 장치의 동작 순서, 타이밍, 보호 단계 상승(Escalation), 진단 기록 및 복구 동작을 검증해야 한다.

견고한 BMS 협조 보호 아키텍처(Robust BMS-Coordinated Protection Architecture)는 센싱(Sensing), 동적 운전 한계(Dynamic Operating Limit), 단계별 고장 대응(Staged Fault Response), 충전기 및 모터 협조, 부하 관리(Load Management), 접촉기 제어, 수동 퓨즈 보호(Passive Fusing), 통신 폴백(Communication Fallback), 진단 및 제어된 복구를 통합한다. 그 목적은 비정상 상태가 파괴적인 고장으로 발전하기 전에 이를 관리하면서 심각한 고장에 대해서는 독립적인 보호 기능을 유지하여 안전하고 선택적이며 신뢰성이 높고 고성능 로봇 플랫폼에 적합한 배터리 시스템을 구현하는 것이다.
