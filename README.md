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

1. El cliente instalado en el equipo del usuario mide métricas de conectividad.

2. Los datos se envían a la API de almacenamiento vía HTTP.

3. La API guarda los registros en una base de datos MongoDB.

4. El módulo de visualización consulta los datos a partir de la API y presenta reportes interactivos.

