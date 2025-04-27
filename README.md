# NetUser404-docs

Sistema de monitoreo de conectividad a internet desde la perspectiva del usuario final.  
NetUser404 permite recolectar, almacenar y visualizar métricas clave de calidad de internet como latencia, velocidad de descarga, tiempos de carga web, y códigos de respuesta HTTP.

Este proyecto se encuentra dividido en tres módulos principales, cada uno desarrollado en un repositorio independiente.

---

## 🔗 Componentes del sistema

- **[NetUser404](https://github.com/mateoprotocol/NetUser404)**  
  Cliente de recolección de datos. Simula la navegación web y mide el desempeño de la conectividad desde el dispositivo del usuario.

- **[NetUser404-api](https://github.com/franyober/netUser404-api/)**  
  API de almacenamiento de métricas. Implementada en FastAPI + MongoDB, recibe y almacena la información recolectada.

- **[NetUser404-visual](https://github.com/franyober/NetUser404-visual)**  
  Dashboard de visualización. Aplicación web desarrollada en Dash para analizar las métricas mediante gráficos y reportes interactivos.

---

## 🛠️ Arquitectura general

![Arquitectura](/assets/Arquitectura_NETUSERv2.png)

### 1. Recolección de métricas

  * El sensor de red NetUser404 (ejecutándose en un dispositivo como una Raspberry Pi) mide de forma periódica la calidad de la conexión a internet.

  * Estas métricas son enviadas a la API NetUser404-api utilizando solicitudes HTTP.

### 2. Almacenamiento de métricas

  * La API NetUser404-api procesa las métricas recibidas.

  * Los datos validados se insertan en una base de datos MongoDB


### 3. Consulta de métricas almacenadas

  * La API NetUser404-api expone múltiples endpoints para consultar la información almacenada en MongoDB.

  * Estos endpoints permiten:

    * Consultar registros filtrados por fecha, BSSID, MAC o URL.

    * Obtener estadísticas agregadas (por ejemplo, promedio de latencias o distribución de códigos HTTP).


### 4. Solicitud de datos desde el dashboard

  * El dashboard NetUser404-visual, que se ejecuta como una aplicación web, realiza peticiones HTTP hacia la API NetUser404-api.

  * El dashboard consulta métricas de conectividad necesarias para generar visualizaciones dinámicas.


### 5. Visualización y análisis de datos

  * Un Administrador accede al Dashboard NetUser404-visual a través de su navegador web.

  * Desde la interfaz gráfica puede:

    * Seleccionar filtros de fecha, dispositivo, red y URL.

    * Visualizar gráficos de latencia, velocidad de descarga, tiempos de carga, y distribución de códigos de estado.

    * Identificar tendencias de rendimiento de la red.

