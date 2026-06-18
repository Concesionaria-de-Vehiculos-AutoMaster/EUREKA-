# EUREKA-
Servidor de Descubrimiento basado en Spring Cloud Netflix Eureka. Actúa como el directorio central para la arquitectura de microservicios, gestionando el registro, monitoreo y localización dinámica de cada servicio

# 🌐 Servidor de Descubrimiento (Eureka Server)

Este repositorio contiene el servidor de registro y descubrimiento basado en **Spring Cloud Netflix Eureka**. Funciona como el componente central (Service Registry) de nuestra arquitectura de microservicios.

## 🎯 ¿Cuál es su función?
En lugar de que cada microservicio y el API Gateway dependan de direcciones IP y puertos fijos (que pueden cambiar), todos los componentes del sistema se conectan a este servidor al arrancar. Eureka mantiene un directorio actualizado en tiempo real de quiénes están en línea y dónde encontrarlos.

## ⚙️ Características principales
* **Registro dinámico:** Microservicios como `ms-vendedores`, `ms-repuestos`, `ms-modelos` y `ms-postventa` se auto-registran aquí al levantarse.
* **Resolución de nombres:** Permite que los servicios se comuniquen entre sí usando sus nombres lógicos (ej. `MS-REPUESTOS`) en lugar de URLs estáticas.
* **Monitoreo de Salud (Heartbeats):** Eureka recibe "latidos" periódicos de los microservicios. Si uno deja de responder, lo da de baja temporalmente del directorio para evitar fallos en cadena.

## 🚀 Ejecución
El servidor está configurado para ejecutarse en el puerto estándar de Eureka:
* **Puerto:** `8761`
* **Dashboard web:** `http://localhost:8761/` (Interfaz gráfica para ver los servicios registrados).
