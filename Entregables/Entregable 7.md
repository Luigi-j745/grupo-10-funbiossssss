Checkpoint 3 – Architecture (¿cómo se va a organizar el sistema conceptualmente?)

1\. Modelos y principios de solución  
○ Elaboren el esquema de funciones, Matriz morfológica y la la tabla de valoración de esta  
según lo mostrado en clase.

**Función global:**  
Mejorar la rehabilitación de Dilan mediante un sistema de monitoreo interactivo que transforme los ejercicios en un juego y permite seguimiento remoto por especialistas.

**Entradas:**

* Señales: movimiento del muñón, presión, datos del sensor, comandos del usuario  
* Energía: batería o fuente eléctrica  
* Materia: prótesis física (pierna) y cuerpo del usuario

**Salidas:**

* Señales: datos procesados, retroalimentación visual y sonora, reporte remoto  
* Energía: movimiento asistido o vibración de aviso  
* Materia: movimiento corregido de la pierna

Esquema de funciones:

| Nivel | Función | Subfunciones | Tipo de flujo |
| :---- | :---- | :---- | :---- |
| **1** | Captar datos del usuario | Medir presión, movimiento, postura | Información |
| **2** | Procesar la información | Filtrar y analizar datos, detectar errores en la marcha | Información |
| **3** | Retroalimentar al usuario | Mostrar puntaje o alerta visual/sonora | Información/Energía |
| **4** | Almacenar y transmitir datos | Guardar historial y enviar al fisioterapeuta | Información |
| **5** | Motivar al usuario | Transformar ejercicios en retos o niveles de juego | Información |
| **6** | Permitir control remoto | Ajustar parámetros desde app/web | Información |

Matriz morfológica:

| Función principal | Alternativa 1 | Alternativa 2 | Alternativa 3 |
| ----- | ----- | ----- | ----- |
| **Captar datos** | Sensor de presión plantar e IMU  | IMU (acelerómetro \+ giroscopio) | Sensor EMG superficial |
| **Procesar datos** | Microcontrolador Arduino | Raspberry Pi | Módulo ESP32 con IA básica |
| **Retroalimentar al usuario** | Pantalla LED integrada | Aplicación móvil gamificada | Señales vibratorias |
| **Transmisión de datos** | Bluetooth | Wi-Fi | GSM (red celular) |
| **Almacenamiento** | SD interna | Nube | Base de datos local |
| **Interfaz de control** | App móvil | Plataforma web | Panel físico con botones |
| **Motivación / gamificación** | Puntos y niveles | Avatares virtuales | Competencias con otros usuarios |

Tabla de valoración:

| Criterio | Peso (%) | Concepto A (bajo costo, Arduino \+ LED) | Concepto B (conectado, ESP32 \+ app móvil) | Concepto C (avanzado, Raspberry \+ nube) |
| ----- | ----- | ----- | ----- | ----- |
| Funcionalidad | 25 | 7 | 9 | 10 |
| Costo | 20 | 10 | 8 | 5 |
| Fiabilidad | 15 | 7 | 9 | 8 |
| Facilidad de uso | 15 | 8 | 10 | 7 |
| Capacidad de monitoreo remoto | 15 | 5 | 10 | 9 |
| Mantenibilidad | 10 | 8 | 8 | 6 |
| **Puntaje total ponderado** | **100%** | **7.4** | **9.0** | **7.8** |

2\. Espacio de solución  
○ Proponga al menos dos bocetos que muestran el concepto de solución que obtuvo más  
puntaje de la tabla de valoración elaborada en el punto 1\. Los bocetos deben estar  
elaborados de acuerdo al formato dado en clase.

<img src="https://drive.usercontent.google.com/download?id=1mCQbDKqJHo2qeq1kHQNBQlAXm8ReuZqV" alt="Boceto" width="600"/>
<img src="https://drive.usercontent.google.com/download?id=1F35DwX3KwNf-butrsI1xpynnOlrsz3ek" alt="Boceto" width="600"/>

**3\. ¿Fabricar o adquirir?**

**Componentes a fabricar**

| Componente | Descripción | Materiales/ Procesos | Justificación técnica |
| ----- | ----- | ----- | ----- |
| Almohadilla circular  | Disco flexible de TPU o silicona médica con sensor de presión y ESP32 incorporados. En el centro y borde lleva velcro médico para fijarse de forma segura al socket​​ | • Moldeo en TPU flexible o silicona medica economica. • Impresión 3D flexible o corte láser de circuitos. • Integración de sensor y ESP32 con batería Li-ion • Encapsulado con silicona delgada • Velcro textil adhesivo en centro y borde. | • Se fabrica para adaptar su diámetro al tamaño del muñón (personalizable). •Oculta la electrónica dentro (segura y estética). •Mantiene bajo costo y comodidad |
| Plantilla sensorial | Inserto flexible con sensores de presión. Se adhiere y ajusta con velcro al pie de la prótesis. | •  EVA o silicona blanda \+ sensor de presión. • Corte manual o molde simple. • Conector FFC hacia el módulo interno | •  Permite medir presión de pisada durante la marcha. • Económica y reemplazable |
| Tobillera electrónica | Banda ligera ajustable con IMU (acelerómetro \+ giroscopio) integrada. Se sujeta con velcro. | • Tela elástica \+ carcasa 3D pequeña (PLA/PETG) • Módulo IMU  | • Registra el ángulo y velocidad de la pisada. • Ligera, no invasiva y económica. |
| PCB personalizada | PCB para integrar ESP32, ADC y conectores para sensores | • Diseño en EasyEDA o KiCad • Fabricación en JLCPCB | • Centraliza conexiones, reduce cables y se adapta a la forma circular. |

**Componentes que se adquirirán**

| Componente | Opción de referencia  | Justificación técnica |
| :---: | :---: | ----- |
| ESP32 o ESP32 mini | Módulo certificado CE/FCC | •Procesamiento y comunicación Bluetooth/WiFi.  • Compacto y económico. |
| Sensor de presión | FSR generico, modelo Interlink 402 o DF9-40 | • Costo bajo, sensible a la presión y flexible.  • Adecuado para muñón y plantilla. |
| IMU (acelerómetro \+ giroscopio) | BNO055, MPU-6050 o MPU-9250 | •Sensor confiable y económico.  •Fases de marcha, ángulos y estabilidad. |
| Batería recargable Li-ion 3.7V  | 18650 o pouch flat. | •Autonomía de 2-3 h. Bajo costo. |
| Módulo ADC (ADS1115) | Módulo estándar | •Aumenta la resolución de las lecturas FSR |

**4\. Secuencia de procesos**  
**Rutina clínica**

| Etapa | Qué se hace | Actor | Resultado |
| ----- | ----- | ----- | ----- |
| Preparación | • Verificar carga de la batería y conexión Bluetooth. • Encender sistema  • Abrir la app del videojuego en el dispositivo de preferencia. | Fisioterapeuta/ técnico | Sistema listo para montaje. |
| Montaje | • Colocar la almohadilla circular dentro del socket, fijandola con el velcro. • Colocar tobillera electronica en el tobillo, ajustandola con velcro. • Insertar la plantilla sensoriada en el pie protesico, ajustandola con velcro. • Confirmar confort y ajuste del paciente. | Fisioterapeuta \+ paciente | Sistema instalado, sin incomodidad |
| Calibración | • Calibrar presion en reposo (munon y pie). • Registrar movimientos de referencia con IMU. • Guardar umbrales base. | Fisioterapeuta \+ app | Retroalimentación en tiempo real |
| Terapia gamificada | • Iniciar el videojuego de rehabilitación • Paciente realiza ejercicios guiados • Almohadilla registra presión en munon • IMU mide angulos y balance • Plantilla mide presion de pisada • App muestra puntajes y alertas visuales. | Paciente, app y fisioterapeuta | Retroalimentación en tiempo real |
| Registro/ seguimiento | • El ESP32 guarda datos y los transmite a la app. • Se generan reportes automáticos (dia/ semana). • El fisioterapeuta revisa resultados | Sistema \+ fisioterapueta remoto | Seguimiento personalizado. |
| Desmontaje/ limpieza | • Apagar módulos • Retirar almohadilla, tobillera y plantilla. • Limpiar con paño húmedo o toallita médica. • Colocar a cargar por USB | Paciente/ técnico | Dispositivo limpio y listo para siguiente uso. |

**Diagrama de flujo**  
[![](https://mermaid.ink/img/pako:eNpVVMFSGzkQ_RWVTkmVYT1gsD2u2i1jY2LAkILdPew4h_ZMexA1I01JGhJw8Uk5bOUT-LG0WrZDLm1J0-_p9euWNzI3BcpUrivzNX8A68XfZ0stxPhDNtcqV-bLx7A9yz5bbMBCrt5-6FT8i1atVQ5WrMCjffsObiTOdY66QCvOrs_Fs4CVVVaMm2Ykxq03Hp3_Ergmm91W3F799cr0SXaHT8oRH3GW0BFPWOXWuI5ojFN86UjcoQqSwDLNNFsY7eERUzFTj4SEqjYPUKiqApEbvaUYiYmpTFDqzYq-oQUxX_wzEnPt0Ho6byrQnlGz-7vRu9KIZG1sFH2-mcSdMAIeW-dxL34axLcrhrzXYH4xkwMBQwlRFLmDrkFnYimzbAKVWu3dnSCloBZkuXFGnJC3p6IBZ2ixgAaJx6EmNDpiamtCVuiY6mIzJflBpW1VQSwVPkFhotJZkt1jkGlEpeqGnAymNuipTzkGr_ZdCNbmPgjNYbUj_xRnInhJNhJelFCzWQVwwpwKaXxrIQ1eirp9-58KEs9__OYF2b9thmHU5eberKhWKifUL2p4NmTltrAo_TLJxlXoFylybYlhtHJjLebsWRiTcG_FhFcZNcsr3ZLSxxbLeM11NlNaFEjeuejzBSUUlFOAN8HJEjXVZdl365FRizBmypPXZCnWxps0usTXFlhxJ8mUSjlWt50OuqdGD9G4m2yKro7jSilsPr6QS-MGytgF6kFYXO_6MgnvII7H7YegPDxEfpni4OBPccZxwu-JluLGxOMk_uzP79--88mU4zmP8rv8acyf7s93-TOOFzxSv51HwGz_YUv0ieOc4yU37D3qMqKu9h-2KD644uU1xwXHG463Sy07srSqkKm3LXZkjbaGsJWbAFxK_4A1LmVKywLX0FZ-KZf6lWAN6P-MqXdIa9ryQaZrqBzt2oY6jlMFpYVfKfzfNTGt9jJNel3mkOlGfpPpQa932O0OesNkeHp6fNQbJB35zMeDw97wKDnpdbsn9HF4_NqRL3zv0WH_-LjbHxwN-8lg0B8m_defI7PIVA?type=png)](https://mermaid.live/edit#pako:eNpVVMFSGzkQ_RWVTkmVYT1gsD2u2i1jY2LAkILdPew4h_ZMexA1I01JGhJw8Uk5bOUT-LG0WrZDLm1J0-_p9euWNzI3BcpUrivzNX8A68XfZ0stxPhDNtcqV-bLx7A9yz5bbMBCrt5-6FT8i1atVQ5WrMCjffsObiTOdY66QCvOrs_Fs4CVVVaMm2Ykxq03Hp3_Ergmm91W3F799cr0SXaHT8oRH3GW0BFPWOXWuI5ojFN86UjcoQqSwDLNNFsY7eERUzFTj4SEqjYPUKiqApEbvaUYiYmpTFDqzYq-oQUxX_wzEnPt0Ho6byrQnlGz-7vRu9KIZG1sFH2-mcSdMAIeW-dxL34axLcrhrzXYH4xkwMBQwlRFLmDrkFnYimzbAKVWu3dnSCloBZkuXFGnJC3p6IBZ2ixgAaJx6EmNDpiamtCVuiY6mIzJflBpW1VQSwVPkFhotJZkt1jkGlEpeqGnAymNuipTzkGr_ZdCNbmPgjNYbUj_xRnInhJNhJelFCzWQVwwpwKaXxrIQ1eirp9-58KEs9__OYF2b9thmHU5eberKhWKifUL2p4NmTltrAo_TLJxlXoFylybYlhtHJjLebsWRiTcG_FhFcZNcsr3ZLSxxbLeM11NlNaFEjeuejzBSUUlFOAN8HJEjXVZdl365FRizBmypPXZCnWxps0usTXFlhxJ8mUSjlWt50OuqdGD9G4m2yKro7jSilsPr6QS-MGytgF6kFYXO_6MgnvII7H7YegPDxEfpni4OBPccZxwu-JluLGxOMk_uzP79--88mU4zmP8rv8acyf7s93-TOOFzxSv51HwGz_YUv0ieOc4yU37D3qMqKu9h-2KD644uU1xwXHG463Sy07srSqkKm3LXZkjbaGsJWbAFxK_4A1LmVKywLX0FZ-KZf6lWAN6P-MqXdIa9ryQaZrqBzt2oY6jlMFpYVfKfzfNTGt9jJNel3mkOlGfpPpQa932O0OesNkeHp6fNQbJB35zMeDw97wKDnpdbsn9HF4_NqRL3zv0WH_-LjbHxwN-8lg0B8m_defI7PIVA)

5\. Técnicas de producción  
○ Seleccionen las técnicas de fabricación adecuadas para cada parte del sistema (ej. impresión 3D en polímeros biocompatibles, mecanizado de precisión, corte láser, etc.):  
Nuestro proyecto consta de una plantilla con sensores la cual se agarra con velcro   en el pie de la prótesis ,junto con una “almohadilla” con sensores en la parte donde hace contacto muñon-protesis, para detectar los puntos de presión

**planta de la protesis:**  
\-suelo-planta:Una capa de TPU o material antideslizante para la base(1mm-2mm para no afectar la marcha)  
\-planta(sensores)-protesis:Capa de TPU o poliuretano,para que se transmita la presión de los sensores sin ser amortiguado

**parte del tobillo(Pylon):**Aqui se encuentra el IMU para recibir los datos sobre el angulo y flexión(unido con velcro o incluso cinta)

**almohadilla muñon-protesis:**  
\-una capa externa de lamina TPU:(Corte manual a forma que se busca o corte laser si se requiere precisión)  
**\-**sensores:cubiertos entre laminas TPU para protegerlos del sudor y fricción

○ Justifiquen la elección considerando costo, durabilidad y facilidad de esterilización.:

Se uso TPU, por ser un material facil de lavar con un  paño húmedo y con un costo de 60 soles aproximado  50x50 cm aprox para lo cual nosotros incluso usaremos poco material para nuestro proyecto  
Se uso Velcro por que el material  es facil de lavar a mano(en caso sea necesario) y nos permite ser “flexibles” al momento de ajustar y poder adaptar según sea necesario ,por un precio aproximado de 20 soles por 15 cm de velcro

6\. Estaciones de trabajo

**Centro de rehabilitación / uso clínico futuro**

El sistema está dirigido a especialistas en rehabilitación (médicos fisiatras y terapeutas físicos), lo que implica su uso en gimnasios de terapia o salas de rehabilitación.

**Consideraciones:** integración con terapias tradicionales y necesidad de supervisión profesional para ajustar la prótesis y validar la información obtenida por los sensores.

**Entorno domiciliario (tele-rehabilitación)**

El sistema incluye la meta de monitoreo remoto del progreso del paciente, reduciendo los viajes desde la zona rural.

**Consideraciones:** conectividad a internet, acceso a dispositivos móviles y capacitación básica de la familia para el uso del sistema.

7\. Automatización:

El sistema de prótesis de Dilan se clasifica como Nivel Medio (Semiautónomo) porque, aunque opera con un alto nivel de automatización asistencial —capturando continuamente datos vitales de presión en el *socket* y cinemática de la marcha para proporcionar retroalimentación inmediata y automática mediante gamificación, e integrando un protocolo *fail-safe* en el *firmware* para activar alertas ante umbrales de seguridad críticos—, la intervención y el juicio humano son irremplazables para la gestión de su condición clínica única. Clínicamente, el nivel Semiautónomo es obligatorio porque Dilan es un paciente pediátrico en crecimiento activo, lo que introduce el riesgo de sobrecrecimiento óseo, un factor biológico que el algoritmo no puede predecir ni gestionar autónomamente. Por lo tanto, el sistema es un registrador y alertador eficiente, pero no puede diagnosticar la causa profunda de los problemas ni tomar acciones físicas correctivas; el terapeuta experto debe interpretar los datos complejos para determinar el momento y la forma de realizar los ajustes físicos y estructurales esenciales en el *socket* protésico, manteniendo la supervisión total y la responsabilidad final.

**→ Escenarios de seguridad:**  
\-Se activa mediante un sistema automático de alerta de umbral configurado en el *firmware*, cuya misión es proteger al paciente y preservar la integridad de los datos. Esta activación automática ocurre en dos escenarios: primero, ante fallas críticas del paciente (como una caída o desmayo), el sistema utiliza los sensores de carga y cinemática para detectar una pérdida abrupta de carga o un patrón errático, lo que provoca que el *firmware* envíe una alerta prioritaria al terapeuta o cuidador y simultáneamente congele la aplicación de gamificación y la adquisición de datos de la sesión. Segundo, ante un fallo del sistema (como un error en el *software* de la *app*), se activa un protocolo *fail-safe* que asegura que el *firmware* continúe operando de forma autónoma para almacenar los datos clínicos localmente en la memoria de la prótesis, mientras se notifica al terapeuta sobre el fallo para que este dirija la recuperación de la información y la intervención necesaria.

8\. Interfaces de red global (IoT y telesalud)  
○ <img src="https://drive.usercontent.google.com/download?id=10aSq-G-BsDPuL00vLxa__hyLtdqzY3AK" alt="Boceto" width="600"/>

○ Los datos recolectados serán:

- Presión en muñón (sensor de presión)  
- Ángulos de movimiento y balance durante la marcha (IMU)  
- Puntajes y avances en los ejercicios gamificados

○ El fisioterapeuta recibirá en la app instalada en su computadora un panel con tablas y gráficas que mostrarán:

- Evolución diaria/semanal de la presión promedio en el muñón  
- Gráfica de estabilidad y rango de movimiento  
- Puntaje obtenido en cada sesión  
- Informe automático o exportable en Excel o PDF

○ Indiquen una medida básica de seguridad o privacidad, como poner contraseña al archivo de datos o no mostrar nombre del paciente, solo un código anónimo, etc.

Los datos del paciente están anonimizados mediante un código único, sin mostrar el nombre real. Además, el acceso a la app y a los reportes estará protegido bajo usuario y contraseña, así se podrá asegurar la confidencialidad de la información clínica.

