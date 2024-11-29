# Sistema de Votación Electrónica usando Blockchain
     ### Montoya Jhonn

Este proyecto es una aplicación web que permite a los usuarios votar por sus candidatos preferidos en una elección. El proyecto usa MongoDB para la gestión de la base de datos y tiene tres colecciones para candidatos, elecciones y usuarios.

## Instalación y Configuración 🔧

### Base de datos
Para crear las colecciones necesarias en la base de datos, consulta los archivos en la carpeta `/server/Models` después de ingresar la URL en el archivo `/server/.env` línea 2.

### Verificación de Correo Electrónico de Terceros 📧
Para habilitar el envío automático de correos electrónicos, agrega la verificación de terceros a tu correo y registra la aplicación para obtener una clave secreta 🔑. Luego, agrega el correo electrónico y la contraseña en el archivo `/server/.env`.

### Ganache ⛓️
Para obtener Ethereum gratis, instala Ganache y agrega el archivo `/smart_contract/truffle-config.js` a tu cuenta. Esto te proporcionará diez cuentas gratuitas con 100 ETH cada una.

### Metamask 🦊
Agrega la extensión de Metamask en Chrome para realizar transacciones.

### Compilación de Contratos 💻
Para compilar el contrato, abre la terminal y navega al directorio `smart_contract` usando el comando `cd smart_contract`. Luego, ejecuta los siguientes comandos:
1. `npm install -g truffle` (si Truffle aún no está instalado).
2. `truffle compile`.
3. `truffle migrate`.

Después de la compilación, sigue los pasos necesarios copiando y pegando la dirección y el archivo `transaction.json`. Una vez compilado:
- Agrega la dirección de la transacción en `Client/utils/Constant.js`.
- Copia el archivo `/smart_contract/build/contracts/Transaction.json` y pégalo en `Client/utils/Transaction.json` para obtener el valor ABI.

### Script en Python (requerido para Autenticación Facial) 🐍
Para instalar los paquetes necesarios para el script de Python, ejecuta:
```bash
pip install opencv-python numpy os face_recognition
Agrega fotos en la carpeta /Face con el mismo nombre de usuario registrado. Si necesitas agregar una URL para las fotos, edita el archivo /server/Controller/encoded.py en la línea 6.

Habilitar o Deshabilitar la Autenticación Facial 🤔
El valor predeterminado es false. Para habilitar o deshabilitar esta función, cambia el valor de isFaceRecognitionEnable en Client/src/Data/Variable.jsx. (Se requieren módulos de Python).

Ejecutar la Aplicación Web 🌐
Ve a la carpeta Client, instala las dependencias necesarias con:
$ npm install
Luego ,
$ npm run start

2. ve a la carpeta server , insttalla las dependencias necesarias con:
$ npm install 
luego ejectura  nodemon index
