# CONTADOR

# Definición del Sprint

El objetivo principal de este sprint es lograr el despliegue exitoso de un Smart Contract funcional en la red de prueba (TestNet) de Stellar, así como su integración completa con una API backend desarrollada en Node.js.

Se busca que el sistema sea capaz de:

* Ejecutar lógica de negocio real en blockchain
* Interactuar correctamente con la red TestNet
* Ser invocado mediante CLI y mediante una API REST
* Validar transacciones mediante hashes verificables

---

# Despliegue del Smart Contract (TestNet)

El contrato inteligente fue desplegado exitosamente en la red TestNet de Stellar utilizando Soroban.

**Red:** TestNet
**Estado:** Activo
**Contract ID:** (Agregar aquí el ID real del contrato)

El contrato es verificable en el explorador de bloques, donde se pueden consultar:

* Transacciones realizadas
* Estado actual del contrato
* Interacciones con la red

Esto garantiza que el contrato no depende de un entorno local.

---

# Descripción del Contrato

Se desarrolló un contrato inteligente tipo Escrow (custodia), el cual permite simular un proceso de intercambio seguro entre dos partes.

El contrato es capaz de:

* Registrar depósitos
* Retener fondos temporalmente
* Liberar fondos a un destinatario autorizado
* Consultar el estado de una transacción

---

# Funciones Implementadas

* deposit
* release
* get_escrow

---

# Criterios de Aceptación

## Lógica del Contrato

* Implementación correcta del flujo de custodia
* Separación clara de responsabilidades
* Uso de estructuras de datos para persistencia
* Validación de estados antes de ejecutar operaciones

---

## Seguridad

Se aplicaron buenas prácticas de seguridad en blockchain:

* Autenticación obligatoria mediante require_auth()
* Prevención de doble ejecución (double spending)
* Validación de condiciones antes de modificar el estado

Nota: Aunque Soroban maneja ciertos aspectos de seguridad internamente, el contrato fue diseñado evitando patrones inseguros.

---

# Arquitectura de la API (Node.js)

Se desarrolló una API REST utilizando Node.js que permite interactuar con el contrato inteligente.

## Tecnologías utilizadas

* Node.js
* Express
* Stellar SDK
* Dotenv

## Características

* Manejo de asincronía con async/await
* Uso de variables de entorno (.env)
* Separación de capas (rutas, controladores, servicios)
* Middleware para manejo de errores

---

# Conectividad y SDK

Se utilizó el SDK oficial de Stellar para establecer la conexión con la blockchain.

## Funcionalidades

* Construcción de transacciones
* Firma criptográfica
* Envío a la red TestNet
* Recepción de hash de transacción

## Buenas prácticas

* Uso de endpoints oficiales
* Manejo de errores de red
* Configuración desacoplada

---

# Pruebas de Integración (End-to-End)

Se realizaron pruebas completas desde la API hasta la blockchain.

## Flujo de prueba

1. Cliente envía petición a la API
2. La API procesa la solicitud
3. Se construye la transacción
4. Se firma con la clave privada
5. Se envía a la red
6. Se obtiene el hash
7. Se valida en el explorador

## Evidencias

* Hash de transacciones: (Agregar ejemplos reales)
* Confirmación en explorador
* Respuestas HTTP exitosas

## Manejo de errores

Se implementó middleware para capturar errores como:

* Transaction Failed
* Problemas de conexión
* Datos inválidos

---

# Documentación de Endpoints

## POST /api/register

Descripción: Registra datos en el contrato inteligente.

Parámetros:

* data

Respuesta:

* hash de la transacción

---

## GET /api/getData

Descripción: Consulta datos almacenados en el contrato.

Respuesta:

* Información registrada

---

## POST /api/execute

Descripción: Ejecuta una operación dentro del contrato.

---

# Instalación y Ejecución

## Requisitos

* Node.js
* Stellar CLI
* Acceso a TestNet

## Pasos

```bash
# Clonar repositorio
git clone <repositorio>

# Instalar dependencias
npm install

# Configurar variables de entorno
SECRET_KEY=tu_llave_privada
PUBLIC_KEY=tu_llave_publica
NETWORK=TestNet

# Ejecutar servidor
npm run dev
```

---

# Configuración del SDK

## Herramientas utilizadas

* Rust
* Soroban SDK
* Stellar CLI

## Comandos principales

```bash
# Inicializar contrato
stellar contract init

# Compilar contrato
stellar contract build

# Desplegar contrato
stellar contract deploy
```

---

# Pruebas

* Compilación exitosa a WASM
* Ejecución en entorno local
* Despliegue en TestNet
* Invocación mediante CLI
* Invocación mediante API REST

---

# Conclusión

El sistema cumple con los requisitos de una arquitectura Web3 completa, integrando correctamente un contrato inteligente en TestNet con una API backend robusta.

Resultados:
<img width="884" height="560" alt="image" src="https://github.com/user-attachments/assets/da07cd92-5038-40ae-8ab7-c5d042808689" />


<img width="816" height="302" alt="image" src="https://github.com/user-attachments/assets/93152505-bff9-4f01-8256-4019b8cded80" />

* Despliegue verificable
  <img width="1364" height="581" alt="image" src="https://github.com/user-attachments/assets/80f72cd6-9c4a-4c5f-a586-e592ee7b5cae" />


---
