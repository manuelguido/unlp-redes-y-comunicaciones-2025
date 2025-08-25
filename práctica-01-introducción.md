# Práctica 1: Introducción a Redes y Comunicaciones

## 1. ¿Qué es una red? ¿Cuál es el principal objetivo para construir una red?

### Concepto
Una **red de computadoras** es un conjunto de dispositivos interconectados (computadoras, servidores, dispositivos móviles, etc.) que pueden comunicarse entre sí e intercambiar información a través de medios de transmisión y protocolos de comunicación.

### Fundamento
El principal objetivo para construir una red es **permitir el intercambio de recursos y información** entre dispositivos distribuidos geográficamente. Esto incluye:

- **Compartir recursos**: Hardware (impresoras, almacenamiento), software, datos
- **Comunicación**: Email, mensajería, videoconferencias
- **Acceso remoto**: Trabajar con recursos ubicados en otras ubicaciones
- **Distribución de carga**: Procesar tareas en múltiples sistemas
- **Redundancia**: Tolerancia a fallos y backup distribuido

### Ejemplos
- Red doméstica: Compartir Internet entre dispositivos
- Red empresarial: Acceso a servidores y aplicaciones corporativas
- Internet: La red global que conecta millones de redes más pequeñas

---

## 2. ¿Qué es Internet? Describa los principales componentes que permiten su funcionamiento.

### Concepto
**Internet** es una red global de redes interconectadas que utiliza protocolos estándar (principalmente TCP/IP) para permitir la comunicación entre millones de dispositivos a nivel mundial.

### Principales Componentes

#### Sistemas Finales (End Systems/Hosts)
- **Clientes**: Computadoras, smartphones, tablets
- **Servidores**: Sistemas que proveen servicios (web, email, DNS)

#### Enlaces de Comunicación
- **Medios físicos**: Fibra óptica, cables de cobre, enlaces inalámbricos
- **Capacidades**: Diferentes anchos de banda (bps, Kbps, Mbps, Gbps)

#### Conmutadores de Paquetes
- **Routers**: Direccionan paquetes entre redes (capa de red)
- **Switches**: Conectan dispositivos en redes locales (capa de enlace)

#### Protocolos
- **TCP/IP**: Conjunto de protocolos que define las reglas de comunicación
- **Aplicación**: HTTP, SMTP, DNS, FTP
- **Control**: ICMP, ARP, DHCP

#### Infraestructura de Servicios
- **ISPs**: Proveedores de servicios de Internet
- **Sistemas autónomos**: Redes administradas independientemente
- **Puntos de intercambio**: IXPs donde se conectan diferentes redes

---

## 3. ¿Qué son las RFCs?

### Concepto
**RFC (Request for Comments)** son documentos técnicos que describen métodos, comportamientos, investigaciones o innovaciones aplicables a Internet y sistemas conectados.

### Fundamento
Las RFCs surgieron como mecanismo para:
- **Documentar protocolos** de manera estándar y pública
- **Facilitar la interoperabilidad** entre diferentes implementaciones
- **Permitir la evolución** gradual y controlada de Internet
- **Mantener un registro histórico** de decisiones técnicas

### Funcionamiento
- Publicadas por la **IETF (Internet Engineering Task Force)**
- Numeradas secuencialmente (ej: RFC 791 para IP, RFC 793 para TCP)
- Estados: Proposed Standard → Draft Standard → Internet Standard
- Una vez publicadas, **nunca se modifican** (se crean nuevas RFCs)

### Ejemplos Importantes
- **RFC 791**: Internet Protocol (IP)
- **RFC 793**: Transmission Control Protocol (TCP)
- **RFC 1034/1035**: Domain Name System (DNS)
- **RFC 2616**: HTTP/1.1

---

## 4. ¿Qué es un protocolo?

### Concepto
Un **protocolo** es un conjunto de reglas y convenciones que definen cómo dos o más entidades se comunican, especificando el formato, orden y acciones que deben realizar durante el intercambio de mensajes.

### Fundamento
Los protocolos son necesarios porque:
- **Estandarizan la comunicación** entre sistemas heterogéneos
- **Definen sintaxis y semántica** de los mensajes
- **Establecen procedimientos** para manejo de errores y excepciones
- **Garantizan interoperabilidad** entre diferentes fabricantes

### Componentes de un Protocolo
1. **Sintaxis**: Formato y estructura de los datos
2. **Semántica**: Significado de cada campo y mensaje
3. **Temporización**: Cuándo y en qué orden se envían los mensajes

### Ejemplos
- **HTTP**: Define cómo navegadores y servidores web intercambian páginas
- **SMTP**: Especifica cómo se transfieren emails entre servidores
- **TCP**: Establece cómo crear conexiones confiables entre aplicaciones

---

## 5. ¿Por qué dos máquinas con distintos sistemas operativos pueden formar parte de una misma red?

### Fundamento
Esto es posible gracias a la **estandarización de protocolos de red** y el **modelo de capas**, que crean una abstracción entre el sistema operativo y la comunicación de red.

### Mecanismos que lo Permiten

#### Protocolos Estándar
- **TCP/IP** es independiente del sistema operativo
- Cada OS implementa el mismo stack de protocolos
- Las **APIs de red** (como sockets) proporcionan interfaces estándar

#### Modelo de Capas
- La **capa de red** abstrae las diferencias del hardware
- Los **protocolos de aplicación** son independientes del OS
- Cada capa oculta los detalles de implementación a las capas superiores

#### Ejemplo Práctico
Una página web puede ser:
- **Servida** por un servidor Linux con Apache
- **Accedida** desde Windows con Chrome
- **Almacenada** en un servidor de base de datos Unix
- **Balanceada** por un switch de red con firmware propietario

Todos funcionan juntos porque implementan los mismos protocolos TCP/IP.

---

## 6. ¿Cuáles son las 2 categorías en las que pueden clasificarse a los sistemas finales o End Systems?

### Categorías

#### 1. Clientes
**Concepto**: Sistemas que inician solicitudes de servicios

**Características**:
- Típicamente se conectan de forma intermitente
- Pueden tener direcciones IP dinámicas
- Consumen servicios de la red

#### 2. Servidores
**Concepto**: Sistemas que proveen servicios y responden a solicitudes

**Características**:
- Están siempre conectados (o con alta disponibilidad)
- Tienen direcciones IP fijas (generalmente)
- Atienden múltiples clientes simultáneamente

### Ejemplo: Aplicación Web Distribuida

**Escenario**: Sistema de e-commerce

#### Clientes
- **Navegador web** (Chrome en laptop): Solicita páginas HTML
- **App móvil** (Android/iOS): Consulta productos y realiza compras
- **Sistema de pagos** (PayPal): Procesa transacciones como cliente

#### Servidores
- **Servidor web** (nginx): Sirve páginas HTML/CSS/JS
- **Servidor de aplicaciones** (Django/Node.js): Procesa lógica de negocio
- **Servidor de base de datos** (PostgreSQL): Almacena productos y usuarios
- **Servidor DNS**: Resuelve nombres de dominio a direcciones IP

**Nota**: Un mismo sistema puede actuar como cliente en algunas interacciones y servidor en otras.

---

## 7. ¿Cuál es la diferencia entre una red conmutada de paquetes de una red conmutada de circuitos?

### Red Conmutada de Circuitos

#### Funcionamiento
- **Establece un circuito dedicado** extremo a extremo antes de la transmisión
- El **ancho de banda se reserva** durante toda la sesión
- Los datos fluyen por el **mismo camino físico** establecido

#### Características
- ✅ **Garantiza ancho de banda** y baja latencia constante
- ✅ **Predecible**: Recursos reservados
- ❌ **Ineficiente**: Recursos desperdiciados cuando no hay transmisión
- ❌ **Costo elevado**: Requiere mantener circuitos activos

#### Ejemplo
**Red telefónica tradicional (PSTN)**: Cuando realizas una llamada, se establece un circuito dedicado que permanece activo durante toda la conversación.

### Red Conmutada de Paquetes

#### Funcionamiento
- **No hay reserva previa** de recursos
- Los datos se dividen en **paquetes independientes**
- Cada paquete puede tomar **rutas diferentes** hacia el destino
- **Multiplexación estadística**: Los recursos se comparten dinámicamente

#### Características
- ✅ **Eficiente**: Mejor utilización de recursos
- ✅ **Flexible**: Adaptación dinámica a condiciones de red
- ✅ **Económica**: Compartición de infraestructura
- ❌ **Variable**: Latencia y ancho de banda no garantizados
- ❌ **Compleja**: Requiere manejo de congestión y errores

#### Ejemplo
**Internet**: Un email se fragmenta en paquetes que pueden viajar por diferentes rutas y llegar en diferente orden, siendo reensamblados en destino.

### Comparación Práctica

| Aspecto | Circuitos | Paquetes |
|---------|-----------|----------|
| **Uso de recursos** | Reserva fija | Compartición dinámica |
| **Latencia** | Constante y baja | Variable |
| **Ancho de banda** | Garantizado | Best effort |
| **Eficiencia** | Baja (recursos ociosos) | Alta |
| **Costo** | Alto | Menor |
| **Aplicaciones típicas** | Voz tradicional | Internet, datos |

---

## 8. Analice qué tipo de red es una red de telefonía y qué tipo de red es Internet.

### Red de Telefonía Tradicional (PSTN)

#### Tipo: Conmutada de Circuitos
**Características**:
- **Establecimiento de llamada**: Proceso de señalización previo
- **Circuito dedicado**: Recursos reservados durante la comunicación
- **Calidad garantizada**: Ancho de banda fijo (64 Kbps por canal de voz)
- **Tarificación por tiempo**: Se cobra por duración de la conexión

**Evolución Moderna**: VoIP y telefonía IP utilizan conmutación de paquetes, pero mantienen conceptos de circuitos virtuales para garantizar calidad de servicio.

### Internet

#### Tipo: Conmutada de Paquetes
**Características**:
- **Sin reserva previa**: No hay establecimiento de circuito
- **Multiplexación estadística**: Recursos compartidos dinámicamente
- **Best effort**: No garantiza calidad de servicio
- **Paquetes independientes**: Cada uno se enruta individualmente
- **Tolerante a fallos**: Rutas alternativas automáticas

### Análisis Comparativo

#### Ventajas de Cada Enfoque

**Telefonía (Circuitos)**:
- Ideal para **comunicación en tiempo real** (voz)
- **Latencia predecible** y constante
- **Calidad garantizada** durante la sesión

**Internet (Paquetes)**:
- **Flexibilidad** para diferentes tipos de tráfico
- **Eficiencia** en el uso de recursos
- **Escalabilidad** para millones de usuarios
- **Económicamente viable** para datos

#### Convergencia Actual
Hoy en día, las redes tienden a **converger**:
- **VoIP**: Voz sobre IP utiliza paquetes pero con QoS
- **MPLS**: Combina flexibilidad de paquetes con garantías de circuitos
- **5G**: Usa slicing de red para diferentes tipos de servicios

---

## 9. Describa brevemente las distintas alternativas que conoce para acceder a Internet en su hogar.

### Tecnologías de Acceso Doméstico

#### 1. Banda Ancha Fija

##### DSL (Digital Subscriber Line)
- **Medio**: Líneas telefónicas de cobre existentes
- **Velocidades**: 1-100 Mbps (asimétricas: mayor bajada que subida)
- **Ventajas**: Infraestructura existente, disponibilidad amplia
- **Desventajas**: Velocidad depende de distancia a central telefónica

##### Cable Módem
- **Medio**: Red de TV por cable (coaxial/fibra híbrida)
- **Velocidades**: 10 Mbps - 1 Gbps
- **Ventajas**: Altas velocidades, infraestructura de TV existente
- **Desventajas**: Ancho de banda compartido en el vecindario

##### Fibra Óptica (FTTH/FTTP)
- **Medio**: Fibra óptica hasta el hogar
- **Velocidades**: 100 Mbps - 10 Gbps (simétrica)
- **Ventajas**: Máxima velocidad, baja latencia, futuro-segura
- **Desventajas**: Costo de instalación, disponibilidad limitada

#### 2. Acceso Inalámbrico

##### 4G/5G Móvil
- **Medio**: Torres de telefonía celular
- **Velocidades**: 5-1000 Mbps (dependiendo de generación y cobertura)
- **Ventajas**: Movilidad, cobertura amplia
- **Desventajas**: Límites de datos, latencia variable

##### Internet Satelital
- **Medio**: Satélites en órbita (LEO, GEO)
- **Velocidades**: 12-500 Mbps
- **Ventajas**: Cobertura en zonas rurales remotas
- **Desventajas**: Alta latencia (GEO), costo elevado, dependiente del clima

##### Wireless Fixed (WISP)
- **Medio**: Enlaces inalámbricos punto a punto
- **Velocidades**: 5-100 Mbps
- **Ventajas**: Instalación rápida en zonas rurales
- **Desventajas**: Línea de vista requerida, limitaciones de distancia

### Comparación por Contexto Argentino

| Tecnología | Disponibilidad | Velocidad Típica | Costo Relativo |
|------------|----------------|------------------|----------------|
| **Fibra óptica** | Ciudades principales | 100-1000 Mbps | Alto |
| **Cable módem** | Zonas urbanas | 50-300 Mbps | Medio |
| **DSL** | Amplia | 10-50 Mbps | Bajo |
| **4G/5G** | Nacional | 10-100 Mbps | Variable |
| **Satelital** | Nacional | 25-100 Mbps | Alto |

---

## 10. ¿Qué ventajas tiene una implementación basada en capas o niveles?

### Principio de Diseño Modular

#### Ventajas Principales

##### 1. **Separación de Responsabilidades**
- Cada capa tiene **funciones específicas** y bien definidas
- **Especialización**: Cada capa resuelve un conjunto particular de problemas
- **Claridad conceptual**: Facilita el entendimiento del sistema completo

##### 2. **Independencia entre Capas**
- **Abstracción**: Las capas superiores no necesitan conocer detalles de implementación de las inferiores
- **Interfaces bien definidas**: Comunicación a través de APIs estándar
- **Flexibilidad**: Cambios en una capa no afectan a las demás

##### 3. **Facilidad de Desarrollo y Mantenimiento**
- **Desarrollo paralelo**: Diferentes equipos pueden trabajar en diferentes capas
- **Testing independiente**: Cada capa puede probarse por separado
- **Debugging simplificado**: Problemas se aíslan por capa

##### 4. **Interoperabilidad**
- **Estándares por capa**: Diferentes fabricantes pueden implementar la misma capa
- **Mix and match**: Combinación de tecnologías de diferentes proveedores
- **Evolución independiente**: Una capa puede evolucionar sin afectar otras

##### 5. **Reutilización**
- **Servicios comunes**: Una capa puede servir a múltiples capas superiores
- **Eficiencia de desarrollo**: No reinventar soluciones para cada aplicación

### Ejemplo Práctico
```
Aplicación Web (Netflix)
├── HTTP/HTTPS (Aplicación) - Streaming de video
├── TCP (Transporte) - Transmisión confiable
├── IP (Red) - Ruteo global
├── Ethernet (Enlace) - Red local
└── Cable/Fibra (Física) - Transmisión de bits
```

Cambiar de cable a WiFi solo afecta las capas Física y Enlace; Netflix sigue funcionando igual.

---

## 11. ¿Cómo se llama la PDU de cada una de las siguientes capas: Aplicación, Transporte, Red y Enlace?

### PDU (Protocol Data Unit) por Capa

| Capa | PDU | Descripción |
|------|-----|-------------|
| **Aplicación** | **Mensaje** | Datos de la aplicación (ej: página HTML, email) |
| **Transporte** | **Segmento** (TCP) / **Datagrama** (UDP) | Datos + header de transporte |
| **Red** | **Paquete** | Segmento + header IP |
| **Enlace** | **Trama (Frame)** | Paquete + header de enlace |

### Proceso de Encapsulación

```
[Datos de Aplicación] 
           ↓ (Aplicación)
[Mensaje]
           ↓ (Transporte - agrega header TCP/UDP)
[Segmento/Datagrama]
           ↓ (Red - agrega header IP)  
[Paquete]
           ↓ (Enlace - agrega header Ethernet)
[Trama]
           ↓ (Física - convierte a señales eléctricas/ópticas)
[Bits]
```

### Ejemplo Concreto
Enviando un email:
1. **Aplicación**: Email completo (mensaje)
2. **Transporte**: Email + header TCP (segmento)
3. **Red**: Segmento + header IP con direcciones origen/destino (paquete)
4. **Enlace**: Paquete + header Ethernet con direcciones MAC (trama)

---

## 12. ¿Qué es la encapsulación? Si una capa realiza la encapsulación de datos, ¿qué capa del nodo receptor realizará el proceso inverso?

### Concepto de Encapsulación

#### Definición
**Encapsulación** es el proceso por el cual cada capa del modelo TCP/IP agrega su propia información de control (header) a los datos recibidos de la capa superior.

#### Proceso en el Emisor
```
Capa de Aplicación:    [Datos]
Capa de Transporte:    [Header TCP][Datos]
Capa de Red:           [Header IP][Header TCP][Datos]  
Capa de Enlace:        [Header Ethernet][Header IP][Header TCP][Datos][Trailer]
```

### Desencapsulación en el Receptor

#### Proceso Inverso
El **proceso inverso** se llama **desencapsulación** y cada capa remueve su propio header:

```
Capa de Enlace:        [Header Ethernet][Header IP][Header TCP][Datos][Trailer]
                                ↓ (remueve header Ethernet)
Capa de Red:           [Header IP][Header TCP][Datos]
                                ↓ (remueve header IP)
Capa de Transporte:    [Header TCP][Datos]
                                ↓ (remueve header TCP)
Capa de Aplicación:    [Datos]
```

### Principio de Correspondencia
**Cada capa realiza la operación inversa de su capa correspondiente**:
- Enlace emisor encapsula → **Enlace receptor desencapsula**
- Red emisor encapsula → **Red receptor desencapsula**  
- Transporte emisor encapsula → **Transporte receptor desencapsula**

### Funciones de Cada Header
- **Ethernet**: Direcciones MAC origen/destino, tipo de protocolo
- **IP**: Direcciones IP origen/destino, TTL, checksum
- **TCP**: Puertos origen/destino, números de secuencia, flags de control

---

## 13. Describa cuáles son las funciones de cada una de las capas del stack TCP/IP.

### Stack TCP/IP (4 Capas)

#### Capa de Aplicación
**Funciones**:
- **Servicios de red para aplicaciones**: Interfaces directas con programas de usuario
- **Protocolos específicos por servicio**: HTTP (web), SMTP (email), DNS (nombres), FTP (archivos)
- **Formato de datos**: Define estructura de mensajes de aplicación

**Responsabilidades**:
- Interpretación y presentación de datos al usuario
- Autenticación y autorización de usuarios
- Compresión y encriptación de datos

**Ejemplos**: Navegador web usando HTTP, cliente de email usando SMTP/POP3

#### Capa de Transporte  
**Funciones**:
- **Multiplexación/Demultiplexación**: Uso de puertos para identificar aplicaciones
- **Control de errores**: Detección y recuperación de datos corruptos (TCP)
- **Control de flujo**: Evitar que el emisor sature al receptor (TCP)
- **Control de congestión**: Adaptarse a condiciones de la red (TCP)

**Protocolos**:
- **TCP**: Confiable, orientado a conexión, control de flujo
- **UDP**: No confiable, sin conexión, mínimo overhead

**Responsabilidades**:
- Segmentación y reensamblado de datos
- Establecimiento, mantenimiento y cierre de conexiones (TCP)
- Entrega ordenada de datos (TCP)

#### Capa de Red (Internet)
**Funciones**:
- **Ruteo**: Determinación del mejor camino entre origen y destino
- **Direccionamiento global**: Uso de direcciones IP únicas
- **Fragmentación**: Adaptación a diferentes MTUs de redes
- **Control de errores básico**: Reportar problemas de entrega (ICMP)

**Protocolos principales**:
- **IP**: Entrega best-effort de paquetes
- **ICMP**: Mensajes de error y control
- **ARP**: Resolución de direcciones IP a MAC

**Responsabilidades**:
- Forwarding de paquetes router por router
- Mantenimiento de tablas de ruteo
- Manejo de diferentes tipos de redes físicas

#### Capa de Enlace (Network Access)
**Funciones**:
- **Acceso al medio físico**: Control de acceso en medios compartidos
- **Framing**: Delimitación de inicio y fin de tramas
- **Detección de errores**: Checksums para integridad en el enlace local
- **Direccionamiento local**: Uso de direcciones MAC para identificación en LAN

**Tecnologías**:
- **Ethernet**: CSMA/CD, switching
- **WiFi (802.11)**: CSMA/CA, asociación a access points
- **PPP**: Conexiones punto a punto

**Responsabilidades**:
- Transmisión confiable entre nodos adyacentes
- Conversión entre direcciones IP y direcciones físicas (ARP)
- Adaptación a diferentes tecnologías de red física

### Interacción entre Capas
Cada capa **utiliza servicios** de la capa inferior y **proporciona servicios** a la capa superior, creando una arquitectura modular que facilita el desarrollo, mantenimiento y evolución de Internet.

---

## 14. Compare el modelo OSI con la implementación TCP/IP.

### Modelos Comparados

#### Modelo OSI (7 Capas)
**Propósito**: Modelo de referencia teórico para entender comunicaciones de red

#### Modelo TCP/IP (4 Capas)  
**Propósito**: Implementación práctica que hace funcionar Internet

### Comparación Estructural

| OSI | TCP/IP | Función Principal |
|-----|--------|-------------------|
| **7. Aplicación** | **Aplicación** | Servicios de red para aplicaciones |
| **6. Presentación** | ↗️ | Formato, encriptación, compresión |
| **5. Sesión** | ↗️ | Establecimiento y gestión de sesiones |
| **4. Transporte** | **Transporte** | Control extremo a extremo (TCP/UDP) |
| **3. Red** | **Internet (Red)** | Ruteo y direccionamiento global (IP) |
| **2. Enlace** | **Acceso a Red** | Acceso al medio físico local |
| **1. Física** | ↗️ | Transmisión de bits |

### Diferencias Clave

#### Filosóficas
**OSI**:
- **Teórico primero**: Modelo diseñado antes de implementar
- **Estructura rígida**: Separación estricta de funciones
- **Académico**: Ideal para enseñanza y comprensión conceptual

**TCP/IP**:
- **Implementación primero**: Desarrollado para hacer funcionar ARPANET/Internet
- **Pragmático**: Las capas se ajustan a necesidades reales
- **Evolutivo**: Ha crecido y cambiado con Internet

#### Estructurales

##### Capas Superiores (OSI: 5-7)
**OSI** separa:
- **Sesión**: Manejo de diálogos y sesiones
- **Presentación**: Formato de datos, encriptación
- **Aplicación**: Interfaz con usuario

**TCP/IP** combina todo en:
- **Aplicación**: Las aplicaciones manejan directamente formato, sesiones y presentación

##### Capas Inferiores (OSI: 1-2)
**OSI** separa:
- **Física**: Características eléctricas, mecánicas
- **Enlace**: Control de acceso al medio, framing

**TCP/IP** combina en:
- **Acceso a Red**: Maneja tanto aspectos físicos como de enlace

### Ventajas y Desventajas

#### Modelo OSI
**Ventajas**:
- ✅ **Didáctico**: Excelente para entender conceptos
- ✅ **Completo**: Cubre todos los aspectos teóricos
- ✅ **Estructurado**: Separación clara de responsabilidades

**Desventajas**:
- ❌ **Complejo**: 7 capas pueden ser excesivas para implementación
- ❌ **Teórico**: No siempre se mapea bien a implementaciones reales

#### Modelo TCP/IP
**Ventajas**:
- ✅ **Práctico**: Ha demostrado funcionar en Internet real
- ✅ **Flexible**: Permite implementaciones variadas
- ✅ **Establecido**: Base de facto de Internet

**Desventajas**:
- ❌ **Menos estructurado**: Funciones mezcladas en algunas capas
- ❌ **Específico**: Diseñado principalmente para TCP/IP

### Uso Actual
- **OSI**: Referencia conceptual para educación y análisis
- **TCP/IP**: Implementación real en todas las redes modernas
- **Híbrido**: Muchos profesionales usan terminología OSI para describir implementaciones TCP/IP

---

## Resumen de Conceptos Clave

### Fundamentos Establecidos
1. **Redes** permiten compartir recursos y comunicación
2. **Internet** es la red de redes global basada en TCP/IP
3. **Protocolos** establecen reglas de comunicación estándar
4. **Estandarización** (RFCs) garantiza interoperabilidad
5. **Modelo de capas** proporciona abstracción y modularidad

### Preparación para Próximas Unidades
Esta base conceptual es fundamental para entender:
- Protocolos específicos de cada capa
- Funcionamiento detallado de TCP, IP, Ethernet
- Servicios avanzados como DNS, HTTP, routing dinámico

---
*Práctica desarrollada siguiendo el programa oficial de Redes y Comunicaciones - UNLP*
