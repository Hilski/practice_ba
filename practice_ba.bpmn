<?xml version="1.0" encoding="UTF-8"?>
<bpmn:definitions xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:bpmn="http://www.omg.org/spec/BPMN/20100524/MODEL" xmlns:bpmndi="http://www.omg.org/spec/BPMN/20100524/DI" xmlns:dc="http://www.omg.org/spec/DD/20100524/DC" xmlns:di="http://www.omg.org/spec/DD/20100524/DI" xmlns:zeebe="http://camunda.org/schema/zeebe/1.0" id="Definitions_1" targetNamespace="http://example.com/bpmn" exporter="Camunda Modeler" exporterVersion="5.33.1">
  <bpmn:process id="SellerOnboardingProcess" isExecutable="true">
    <bpmn:laneSet>
      <bpmn:lane id="lane_supplier" name="Поставщик" />
      <bpmn:lane id="lane_platform" name="Платформа" />
      <bpmn:lane id="lane_admin" name="Администратор" />
    </bpmn:laneSet>
    <bpmn:startEvent id="StartEvent_1" name="Начало регистрации" />
    <bpmn:task id="Task_FillForm" name="Заполнить регистрационную форму" />
    <bpmn:task id="Task_ValidateData" name="Проверка данных" />
    <bpmn:exclusiveGateway id="Gateway_DataValid" name="Данные корректны?" />
    <bpmn:task id="Task_CheckSeller" name="Проверка продавца (KYC)" />
    <bpmn:exclusiveGateway id="Gateway_SellerApproved" name="Продавец одобрен?" />
    <bpmn:task id="Task_CreateCabinet" name="Создать личный кабинет" />
    <bpmn:task id="Task_LoginCabinet" name="Войти в кабинет" />
    <bpmn:task id="Task_CreateProductCard" name="Создать карточку товара" />
    <bpmn:task id="Task_ModerateProduct" name="Модерация карточки" />
    <bpmn:exclusiveGateway id="Gateway_ProductApproved" name="Карточка одобрена?" />
    <bpmn:task id="Task_PublishProduct" name="Опубликовать товар" />
    <bpmn:endEvent id="EndEvent_Success" name="Товар опубликован" />
    <bpmn:endEvent id="EndEvent_Reject" name="Завершено с отказом" />
    <bpmn:sequenceFlow id="flow1" sourceRef="StartEvent_1" targetRef="Task_FillForm" />
    <bpmn:sequenceFlow id="flow2" sourceRef="Task_FillForm" targetRef="Task_ValidateData" />
    <bpmn:sequenceFlow id="flow3" sourceRef="Task_ValidateData" targetRef="Gateway_DataValid" />
    <bpmn:sequenceFlow id="flow4" name="Да" sourceRef="Gateway_DataValid" targetRef="Task_CheckSeller" />
    <bpmn:sequenceFlow id="flow5" name="Нет" sourceRef="Gateway_DataValid" targetRef="EndEvent_Reject" />
    <bpmn:sequenceFlow id="flow6" sourceRef="Task_CheckSeller" targetRef="Gateway_SellerApproved" />
    <bpmn:sequenceFlow id="flow7" name="Да" sourceRef="Gateway_SellerApproved" targetRef="Task_CreateCabinet" />
    <bpmn:sequenceFlow id="flow8" name="Нет" sourceRef="Gateway_SellerApproved" targetRef="EndEvent_Reject" />
    <bpmn:sequenceFlow id="flow9" sourceRef="Task_CreateCabinet" targetRef="Task_LoginCabinet" />
    <bpmn:sequenceFlow id="flow10" sourceRef="Task_LoginCabinet" targetRef="Task_CreateProductCard" />
    <bpmn:sequenceFlow id="flow11" sourceRef="Task_CreateProductCard" targetRef="Task_ModerateProduct" />
    <bpmn:sequenceFlow id="flow12" sourceRef="Task_ModerateProduct" targetRef="Gateway_ProductApproved" />
    <bpmn:sequenceFlow id="flow13" name="Да" sourceRef="Gateway_ProductApproved" targetRef="Task_PublishProduct" />
    <bpmn:sequenceFlow id="flow14" name="Нет" sourceRef="Gateway_ProductApproved" targetRef="EndEvent_Reject" />
    <bpmn:sequenceFlow id="flow15" sourceRef="Task_PublishProduct" targetRef="EndEvent_Success" />
  </bpmn:process>
  <bpmn:collaboration id="Collaboration_1">
    <bpmn:participant id="Participant_Supplier" name="Поставщик" processRef="SellerOnboardingProcess" />
    <bpmn:participant id="Participant_Platform" name="Платформа" />
    <bpmn:participant id="Participant_Admin" name="Администратор" />
    <bpmn:participant id="Participant_0p8rgii" processRef="Process_0nqq03o" />
  </bpmn:collaboration>
  <bpmn:process id="Process_0nqq03o" isExecutable="false">
    <bpmn:laneSet id="LaneSet_1dvdzff">
      <bpmn:lane id="Lane_1wlyaic" name="Продавец">
        <bpmn:flowNodeRef>Event_0d84801</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Activity_0ujgth7</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Event_1fnjbpj</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Event_04gevrk</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Event_0jz3rtq</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Activity_0sx7ig4</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Event_1f5somi</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Event_0wxuwrj</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Event_1q0aojy</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Event_05i1ef4</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Event_0w5bf8c</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Event_08yisjo</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Activity_0rtuwm7</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Activity_02cr288</bpmn:flowNodeRef>
      </bpmn:lane>
      <bpmn:lane id="Lane_1tk81ls" name="Платформа">
        <bpmn:flowNodeRef>Activity_0fwvq75</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Gateway_13xpqzb</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Activity_0fmsw2s</bpmn:flowNodeRef>
      </bpmn:lane>
      <bpmn:lane id="Lane_0covk5u" name="Администратор">
        <bpmn:flowNodeRef>Gateway_0qtua6i</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Activity_0srou16</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Gateway_02xviee</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Activity_1h9zsqa</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Activity_116wuak</bpmn:flowNodeRef>
        <bpmn:flowNodeRef>Activity_1nydjn7</bpmn:flowNodeRef>
      </bpmn:lane>
    </bpmn:laneSet>
    <bpmn:startEvent id="Event_0d84801" name="Начало регистрации">
      <bpmn:outgoing>Flow_04bub8s</bpmn:outgoing>
    </bpmn:startEvent>
    <bpmn:task id="Activity_0ujgth7" name="Зайти на страницу регистрации">
      <bpmn:incoming>Flow_04bub8s</bpmn:incoming>
      <bpmn:outgoing>Flow_0r4r4n3</bpmn:outgoing>
    </bpmn:task>
    <bpmn:serviceTask id="Activity_0fwvq75" name="Проверить данные">
      <bpmn:incoming>Flow_1h99cx9</bpmn:incoming>
      <bpmn:outgoing>Flow_1091wa5</bpmn:outgoing>
    </bpmn:serviceTask>
    <bpmn:exclusiveGateway id="Gateway_13xpqzb" name="Данные верны?">
      <bpmn:incoming>Flow_1091wa5</bpmn:incoming>
      <bpmn:outgoing>Flow_0fqxqwl</bpmn:outgoing>
      <bpmn:outgoing>Flow_17kk1mc</bpmn:outgoing>
    </bpmn:exclusiveGateway>
    <bpmn:exclusiveGateway id="Gateway_0qtua6i" name="Одобрено?">
      <bpmn:incoming>Flow_0ui3arb</bpmn:incoming>
      <bpmn:outgoing>Flow_0ihk63i</bpmn:outgoing>
      <bpmn:outgoing>Flow_1oxseop</bpmn:outgoing>
    </bpmn:exclusiveGateway>
    <bpmn:task id="Activity_0srou16" name="Создать кабинет">
      <bpmn:incoming>Flow_1oxseop</bpmn:incoming>
      <bpmn:outgoing>Flow_0y36d0d</bpmn:outgoing>
    </bpmn:task>
    <bpmn:serviceTask id="Activity_0fmsw2s" name="Отправить на проверку">
      <bpmn:incoming>Flow_17kk1mc</bpmn:incoming>
      <bpmn:outgoing>Flow_0rtyqqu</bpmn:outgoing>
    </bpmn:serviceTask>
    <bpmn:intermediateCatchEvent id="Event_1fnjbpj" name="Отказано">
      <bpmn:incoming>Flow_0fqxqwl</bpmn:incoming>
      <bpmn:outgoing>Flow_063kpbv</bpmn:outgoing>
      <bpmn:messageEventDefinition id="MessageEventDefinition_0e0ri3e" />
    </bpmn:intermediateCatchEvent>
    <bpmn:intermediateCatchEvent id="Event_04gevrk" name="Отказано">
      <bpmn:incoming>Flow_0ihk63i</bpmn:incoming>
      <bpmn:outgoing>Flow_1gl85qq</bpmn:outgoing>
      <bpmn:messageEventDefinition id="MessageEventDefinition_08htd7v" />
    </bpmn:intermediateCatchEvent>
    <bpmn:intermediateCatchEvent id="Event_0jz3rtq" name="Кабинет создан">
      <bpmn:incoming>Flow_0y36d0d</bpmn:incoming>
      <bpmn:outgoing>Flow_0h9dovq</bpmn:outgoing>
      <bpmn:messageEventDefinition id="MessageEventDefinition_1n1re31" />
    </bpmn:intermediateCatchEvent>
    <bpmn:task id="Activity_0sx7ig4" name="Войти в кабинет">
      <bpmn:incoming>Flow_0h9dovq</bpmn:incoming>
      <bpmn:outgoing>Flow_1mp5fys</bpmn:outgoing>
    </bpmn:task>
    <bpmn:intermediateCatchEvent id="Event_1f5somi" name="Отказано">
      <bpmn:incoming>Flow_0962arc</bpmn:incoming>
      <bpmn:outgoing>Flow_1duz7or</bpmn:outgoing>
      <bpmn:messageEventDefinition id="MessageEventDefinition_0r8iy6i" />
    </bpmn:intermediateCatchEvent>
    <bpmn:intermediateCatchEvent id="Event_0wxuwrj" name="Товар опубликован">
      <bpmn:incoming>Flow_0i4uiv6</bpmn:incoming>
      <bpmn:outgoing>Flow_0afq3l4</bpmn:outgoing>
      <bpmn:messageEventDefinition id="MessageEventDefinition_0n3w3cp" />
    </bpmn:intermediateCatchEvent>
    <bpmn:endEvent id="Event_1q0aojy">
      <bpmn:incoming>Flow_0afq3l4</bpmn:incoming>
    </bpmn:endEvent>
    <bpmn:exclusiveGateway id="Gateway_02xviee" name="Одобрена?">
      <bpmn:incoming>Flow_0c3ela5</bpmn:incoming>
      <bpmn:outgoing>Flow_0962arc</bpmn:outgoing>
      <bpmn:outgoing>Flow_0p7vibc</bpmn:outgoing>
    </bpmn:exclusiveGateway>
    <bpmn:serviceTask id="Activity_1h9zsqa" name="Опубликовать товар">
      <bpmn:incoming>Flow_0p7vibc</bpmn:incoming>
      <bpmn:outgoing>Flow_0i4uiv6</bpmn:outgoing>
    </bpmn:serviceTask>
    <bpmn:endEvent id="Event_05i1ef4">
      <bpmn:incoming>Flow_063kpbv</bpmn:incoming>
      <bpmn:terminateEventDefinition id="TerminateEventDefinition_0j33xkx" />
    </bpmn:endEvent>
    <bpmn:endEvent id="Event_0w5bf8c">
      <bpmn:incoming>Flow_1gl85qq</bpmn:incoming>
      <bpmn:terminateEventDefinition id="TerminateEventDefinition_0pzc88q" />
    </bpmn:endEvent>
    <bpmn:endEvent id="Event_08yisjo">
      <bpmn:incoming>Flow_1duz7or</bpmn:incoming>
      <bpmn:terminateEventDefinition id="TerminateEventDefinition_0z8j63r" />
    </bpmn:endEvent>
    <bpmn:userTask id="Activity_116wuak" name="Проверить карточку товара">
      <bpmn:extensionElements>
        <zeebe:userTask />
      </bpmn:extensionElements>
      <bpmn:incoming>Flow_0n8607m</bpmn:incoming>
      <bpmn:outgoing>Flow_0c3ela5</bpmn:outgoing>
    </bpmn:userTask>
    <bpmn:userTask id="Activity_1nydjn7" name="Проверить продавца">
      <bpmn:extensionElements>
        <zeebe:userTask />
      </bpmn:extensionElements>
      <bpmn:incoming>Flow_0rtyqqu</bpmn:incoming>
      <bpmn:outgoing>Flow_0ui3arb</bpmn:outgoing>
    </bpmn:userTask>
    <bpmn:manualTask id="Activity_0rtuwm7" name="Заполнить регистрационную форму">
      <bpmn:incoming>Flow_0r4r4n3</bpmn:incoming>
      <bpmn:outgoing>Flow_1h99cx9</bpmn:outgoing>
    </bpmn:manualTask>
    <bpmn:manualTask id="Activity_02cr288" name="Создать карточку товара">
      <bpmn:incoming>Flow_1mp5fys</bpmn:incoming>
      <bpmn:outgoing>Flow_0n8607m</bpmn:outgoing>
    </bpmn:manualTask>
    <bpmn:sequenceFlow id="Flow_04bub8s" sourceRef="Event_0d84801" targetRef="Activity_0ujgth7" />
    <bpmn:sequenceFlow id="Flow_0r4r4n3" sourceRef="Activity_0ujgth7" targetRef="Activity_0rtuwm7" />
    <bpmn:sequenceFlow id="Flow_1h99cx9" sourceRef="Activity_0rtuwm7" targetRef="Activity_0fwvq75" />
    <bpmn:sequenceFlow id="Flow_1091wa5" sourceRef="Activity_0fwvq75" targetRef="Gateway_13xpqzb" />
    <bpmn:sequenceFlow id="Flow_0fqxqwl" name="Нет" sourceRef="Gateway_13xpqzb" targetRef="Event_1fnjbpj" />
    <bpmn:sequenceFlow id="Flow_17kk1mc" name="Да" sourceRef="Gateway_13xpqzb" targetRef="Activity_0fmsw2s" />
    <bpmn:sequenceFlow id="Flow_0ui3arb" sourceRef="Activity_1nydjn7" targetRef="Gateway_0qtua6i" />
    <bpmn:sequenceFlow id="Flow_0ihk63i" name="Нет" sourceRef="Gateway_0qtua6i" targetRef="Event_04gevrk" />
    <bpmn:sequenceFlow id="Flow_1oxseop" name="Да" sourceRef="Gateway_0qtua6i" targetRef="Activity_0srou16" />
    <bpmn:sequenceFlow id="Flow_0y36d0d" sourceRef="Activity_0srou16" targetRef="Event_0jz3rtq" />
    <bpmn:sequenceFlow id="Flow_0rtyqqu" sourceRef="Activity_0fmsw2s" targetRef="Activity_1nydjn7" />
    <bpmn:sequenceFlow id="Flow_063kpbv" sourceRef="Event_1fnjbpj" targetRef="Event_05i1ef4" />
    <bpmn:sequenceFlow id="Flow_1gl85qq" sourceRef="Event_04gevrk" targetRef="Event_0w5bf8c" />
    <bpmn:sequenceFlow id="Flow_0h9dovq" sourceRef="Event_0jz3rtq" targetRef="Activity_0sx7ig4" />
    <bpmn:sequenceFlow id="Flow_1mp5fys" sourceRef="Activity_0sx7ig4" targetRef="Activity_02cr288" />
    <bpmn:sequenceFlow id="Flow_0962arc" name="Нет" sourceRef="Gateway_02xviee" targetRef="Event_1f5somi" />
    <bpmn:sequenceFlow id="Flow_1duz7or" sourceRef="Event_1f5somi" targetRef="Event_08yisjo" />
    <bpmn:sequenceFlow id="Flow_0i4uiv6" sourceRef="Activity_1h9zsqa" targetRef="Event_0wxuwrj" />
    <bpmn:sequenceFlow id="Flow_0afq3l4" sourceRef="Event_0wxuwrj" targetRef="Event_1q0aojy" />
    <bpmn:sequenceFlow id="Flow_0c3ela5" sourceRef="Activity_116wuak" targetRef="Gateway_02xviee" />
    <bpmn:sequenceFlow id="Flow_0p7vibc" name="Да" sourceRef="Gateway_02xviee" targetRef="Activity_1h9zsqa" />
    <bpmn:sequenceFlow id="Flow_0n8607m" sourceRef="Activity_02cr288" targetRef="Activity_116wuak" />
  </bpmn:process>
  <bpmndi:BPMNDiagram id="BPMNDiagram_SellerOnboarding">
    <bpmndi:BPMNPlane id="BPMNPlane_SellerOnboarding" bpmnElement="Collaboration_1">
      <bpmndi:BPMNShape id="Participant_0p8rgii_di" bpmnElement="Participant_0p8rgii" isHorizontal="true">
        <dc:Bounds x="160" y="80" width="1908" height="420" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Lane_1wlyaic_di" bpmnElement="Lane_1wlyaic" isHorizontal="true">
        <dc:Bounds x="190" y="80" width="1878" height="140" />
        <bpmndi:BPMNLabel />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Lane_1tk81ls_di" bpmnElement="Lane_1tk81ls" isHorizontal="true">
        <dc:Bounds x="190" y="220" width="1878" height="130" />
        <bpmndi:BPMNLabel />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Lane_0covk5u_di" bpmnElement="Lane_0covk5u" isHorizontal="true">
        <dc:Bounds x="190" y="350" width="1878" height="150" />
        <bpmndi:BPMNLabel />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Event_0d84801_di" bpmnElement="Event_0d84801">
        <dc:Bounds x="232" y="132" width="36" height="36" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="218" y="175" width="64" height="27" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Activity_0ujgth7_di" bpmnElement="Activity_0ujgth7">
        <dc:Bounds x="320" y="110" width="100" height="80" />
        <bpmndi:BPMNLabel />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Activity_038bmti_di" bpmnElement="Activity_0fwvq75">
        <dc:Bounds x="490" y="250" width="100" height="80" />
        <bpmndi:BPMNLabel />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Gateway_13xpqzb_di" bpmnElement="Gateway_13xpqzb" isMarkerVisible="true">
        <dc:Bounds x="645" y="265" width="50" height="50" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="630" y="323" width="80" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Gateway_0qtua6i_di" bpmnElement="Gateway_0qtua6i" isMarkerVisible="true">
        <dc:Bounds x="895" y="405" width="50" height="50" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="891" y="462" width="58" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Activity_0srou16_di" bpmnElement="Activity_0srou16">
        <dc:Bounds x="1000" y="390" width="100" height="80" />
        <bpmndi:BPMNLabel />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Activity_0t2rlwx_di" bpmnElement="Activity_0fmsw2s">
        <dc:Bounds x="750" y="250" width="100" height="80" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Event_1w8aumk_di" bpmnElement="Event_1fnjbpj">
        <dc:Bounds x="712" y="132" width="36" height="36" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="706" y="102" width="48" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Event_1gol59n_di" bpmnElement="Event_04gevrk">
        <dc:Bounds x="962" y="132" width="36" height="36" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="956" y="102" width="48" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Event_0dailvs_di" bpmnElement="Event_0jz3rtq">
        <dc:Bounds x="1162" y="132" width="36" height="36" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="1140" y="102" width="80" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Activity_0sx7ig4_di" bpmnElement="Activity_0sx7ig4">
        <dc:Bounds x="1260" y="110" width="100" height="80" />
        <bpmndi:BPMNLabel />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Event_0utgei8_di" bpmnElement="Event_1f5somi">
        <dc:Bounds x="1652" y="132" width="36" height="36" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="1646" y="102" width="48" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Event_0ep3gw4_di" bpmnElement="Event_0wxuwrj">
        <dc:Bounds x="1872" y="132" width="36" height="36" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="1857" y="102" width="66" height="27" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Event_1q0aojy_di" bpmnElement="Event_1q0aojy">
        <dc:Bounds x="1952" y="132" width="36" height="36" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Gateway_02xviee_di" bpmnElement="Gateway_02xviee" isMarkerVisible="true">
        <dc:Bounds x="1585" y="405" width="50" height="50" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="1581" y="465" width="58" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Activity_14wdvc5_di" bpmnElement="Activity_1h9zsqa">
        <dc:Bounds x="1720" y="390" width="100" height="80" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Event_1gbywhv_di" bpmnElement="Event_05i1ef4">
        <dc:Bounds x="782" y="132" width="36" height="36" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Event_0tjw5ij_di" bpmnElement="Event_0w5bf8c">
        <dc:Bounds x="1032" y="132" width="36" height="36" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Event_053zud4_di" bpmnElement="Event_08yisjo">
        <dc:Bounds x="1722" y="132" width="36" height="36" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Activity_1c9jphg_di" bpmnElement="Activity_116wuak">
        <dc:Bounds x="1430" y="390" width="100" height="80" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Activity_1ihx31h_di" bpmnElement="Activity_1nydjn7">
        <dc:Bounds x="750" y="390" width="100" height="80" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Activity_0h5p6h9_di" bpmnElement="Activity_0rtuwm7">
        <dc:Bounds x="490" y="110" width="100" height="80" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNShape id="Activity_1geveyf_di" bpmnElement="Activity_02cr288">
        <dc:Bounds x="1430" y="110" width="100" height="80" />
      </bpmndi:BPMNShape>
      <bpmndi:BPMNEdge id="Flow_1h99cx9_di" bpmnElement="Flow_1h99cx9">
        <di:waypoint x="540" y="190" />
        <di:waypoint x="540" y="250" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_1091wa5_di" bpmnElement="Flow_1091wa5">
        <di:waypoint x="590" y="290" />
        <di:waypoint x="645" y="290" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_0fqxqwl_di" bpmnElement="Flow_0fqxqwl">
        <di:waypoint x="670" y="265" />
        <di:waypoint x="670" y="150" />
        <di:waypoint x="712" y="150" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="676" y="176" width="20" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_063kpbv_di" bpmnElement="Flow_063kpbv">
        <di:waypoint x="748" y="150" />
        <di:waypoint x="782" y="150" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_17kk1mc_di" bpmnElement="Flow_17kk1mc">
        <di:waypoint x="695" y="290" />
        <di:waypoint x="750" y="290" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="713" y="273" width="13" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_0rtyqqu_di" bpmnElement="Flow_0rtyqqu">
        <di:waypoint x="800" y="330" />
        <di:waypoint x="800" y="390" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_0ui3arb_di" bpmnElement="Flow_0ui3arb">
        <di:waypoint x="850" y="430" />
        <di:waypoint x="895" y="430" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_0ihk63i_di" bpmnElement="Flow_0ihk63i">
        <di:waypoint x="920" y="405" />
        <di:waypoint x="920" y="150" />
        <di:waypoint x="962" y="150" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="925" y="176" width="20" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_1gl85qq_di" bpmnElement="Flow_1gl85qq">
        <di:waypoint x="998" y="150" />
        <di:waypoint x="1032" y="150" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_1oxseop_di" bpmnElement="Flow_1oxseop">
        <di:waypoint x="945" y="430" />
        <di:waypoint x="1000" y="430" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="966" y="412" width="13" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_0y36d0d_di" bpmnElement="Flow_0y36d0d">
        <di:waypoint x="1100" y="430" />
        <di:waypoint x="1131" y="430" />
        <di:waypoint x="1131" y="150" />
        <di:waypoint x="1162" y="150" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_0h9dovq_di" bpmnElement="Flow_0h9dovq">
        <di:waypoint x="1198" y="150" />
        <di:waypoint x="1260" y="150" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_1mp5fys_di" bpmnElement="Flow_1mp5fys">
        <di:waypoint x="1360" y="150" />
        <di:waypoint x="1430" y="150" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_0n8607m_di" bpmnElement="Flow_0n8607m">
        <di:waypoint x="1480" y="190" />
        <di:waypoint x="1480" y="390" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_0c3ela5_di" bpmnElement="Flow_0c3ela5">
        <di:waypoint x="1530" y="430" />
        <di:waypoint x="1585" y="430" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_0962arc_di" bpmnElement="Flow_0962arc">
        <di:waypoint x="1610" y="405" />
        <di:waypoint x="1610" y="150" />
        <di:waypoint x="1652" y="150" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="1615" y="176" width="20" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_1duz7or_di" bpmnElement="Flow_1duz7or">
        <di:waypoint x="1688" y="150" />
        <di:waypoint x="1722" y="150" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_0p7vibc_di" bpmnElement="Flow_0p7vibc">
        <di:waypoint x="1635" y="430" />
        <di:waypoint x="1720" y="430" />
        <bpmndi:BPMNLabel>
          <dc:Bounds x="1671" y="412" width="13" height="14" />
        </bpmndi:BPMNLabel>
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_0i4uiv6_di" bpmnElement="Flow_0i4uiv6">
        <di:waypoint x="1820" y="430" />
        <di:waypoint x="1851" y="430" />
        <di:waypoint x="1851" y="150" />
        <di:waypoint x="1872" y="150" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_0afq3l4_di" bpmnElement="Flow_0afq3l4">
        <di:waypoint x="1908" y="150" />
        <di:waypoint x="1952" y="150" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_04bub8s_di" bpmnElement="Flow_04bub8s">
        <di:waypoint x="268" y="150" />
        <di:waypoint x="320" y="150" />
      </bpmndi:BPMNEdge>
      <bpmndi:BPMNEdge id="Flow_0r4r4n3_di" bpmnElement="Flow_0r4r4n3">
        <di:waypoint x="420" y="150" />
        <di:waypoint x="490" y="150" />
      </bpmndi:BPMNEdge>
    </bpmndi:BPMNPlane>
  </bpmndi:BPMNDiagram>
</bpmn:definitions>
