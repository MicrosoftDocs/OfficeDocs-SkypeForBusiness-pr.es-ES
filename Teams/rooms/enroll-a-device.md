---
title: Inscribir un dispositivo de sala de Teams en Servicios administrados
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Incorporación Salas de Teams dispositivos a servicios administrados
f1keywords: ''
ms.openlocfilehash: 901cf212d6eaeb7ca98b8a158de517b0687ba517
ms.sourcegitcommit: 5bb00d639828c744951a39705fefe81ed6698efe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2022
ms.locfileid: "66167324"
---
# <a name="enroll-device-into-managed-service"></a>Inscribir el dispositivo en un servicio administrado

La implementación requiere la incorporación Salas de Microsoft Teams dispositivos a los servicios administrados Salas de Microsoft Teams. El agente de servicio de supervisión se usa con sistemas de salas de Microsoft Teams certificadas (MTR) y periféricos.

## <a name="prerequisites"></a>Requisitos previos

Sigue estos procedimientos para configurar el hardware antes de intentar el proceso de inscripción:

### <a name="adding-proxy-settings-optional"></a>Agregar configuración de proxy (opcional)

1. Inicie sesión como administrador siguiendo [realizando operaciones como el usuario Administración del dispositivo MTR](#performing-operations-as-the-admin-user-of-the-mtr-device).
1. En el Windows campo ***Search** _ (sección inferior izquierda de la pantalla), escriba _ *cmd** (mantenga presionada la pantalla o seleccione con la derecha y elija **_Ejecutar como administrador_**).
1. Ejecute el siguiente comando (son importantes las comillas dobles al final del comando):

   - Si se usa un único ***servidor proxy***: `bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY <proxyserver>:<port> ""`

     *Ejemplo:*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY contosoproxy.corp.net:8080 ""
     ```

   - Si usa un archivo ***pac*** : `bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url>`

     *Ejemplo:*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT `http://contosoproxy.corp.net/proxy.pac`
     ```

### <a name="enabling-tpm-settings"></a>Habilitación de la configuración de TPM

> [!NOTE]
> El TPM debe estar habilitado para inscribirse en el servicio administrado.

Si el TPM en un dispositivo Intel NUC está deshabilitado, habilite TPM en estos dispositivos como se indica a continuación:

1. Conecte el teclado a un dispositivo NUC.
1. Reinicia el dispositivo.
1. Para mostrar la pantalla bios, presione **F2** rápidamente.
1. Seleccione **Avanzadas**.
1. Selecciona **Seguridad**.
1. En el lado derecho debajo de Características de seguridad, habilite la **tecnología Intel Platform Trust Technology**.
1. Para guardar la configuración, presione **F10**.
1. En el cuadro de confirmación, selecciona **Sí**.

## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>Realizar operaciones como el usuario Administración del dispositivo MTR

Algunos procedimientos de configuración e instalación requieren que inicies sesión en el dispositivo como administrador.

Para iniciar sesión en el dispositivo como administrador (administrador local):

1. Asegúrate de colgar las llamadas en curso y volver a la pantalla principal.
1. En la interfaz de usuario de sala de Microsoft Teams, selecciona **Más** y, a continuación, selecciona **Configuración**, donde se te pedirá la contraseña de administrador local en el dispositivo (la contraseña predeterminada es **_sfb_**).
1. Selecciona **Configuración** y, a continuación, selecciona **Windows Configuración** para acceder a Windows como administrador local.

1. En la lista de usuarios que se muestra en la pantalla de inicio de sesión de Windows, selecciona **Administrador** (o el correspondiente administrador local del dispositivo).

> [!NOTE]
> Si el equipo está *unido a un dominio*, elige **Otro usuario** y, a continuación, usa **.\admin** o el nombre de usuario del administrador local configurado en el dispositivo como nombre de usuario.

Para volver a la aplicación Salas de Microsoft Teams después de realizar las tareas administrativas necesarias:

1. En la ***menú Inicio de Windows***, cierre sesión en la cuenta de Administración.
1. Vuelve a Salas de Microsoft Teams seleccionando el icono de cuenta de usuario en el extremo izquierdo de la pantalla y, a continuación, seleccionando **Skype**.

> [!NOTE]
> Si la Skype usuario no aparece en la lista, seleccione Otro usuario, escriba ***.\skype*** como el nombre de usuario e inicie sesión.

## <a name="urls-required-for-communication"></a>Direcciones URL necesarias para la comunicación

 > [!NOTE]
 > Todo el tráfico de red entre el agente de dispositivos MTR y el portal de servicios de Salas de Microsoft Teams : Servicios administrados es SSL a través del puerto 443 *.*  Vea [Office 365 direcciones URL e intervalos de direcciones IP: Microsoft 365 Enterprise | Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

Los siguientes hosts deben estar permitidos si tienes habilitada la **lista de permitidos de tráfico** en el entorno empresarial:

agent.rooms.microsoft.com<br>
global.azure-devices-provisioning.net<br>
gj3ftstorage.blob.core.windows.net<br>
mmrstgnoamiot.azure-devices.net<br>
mmrstgnoamstor.blob.core.windows.net<br>
mmrprodapaciot.azure-devices.net<br>
mmrprodapacstor.blob.core.windows.net<br>
mmrprodemeaiot.azure-devices.net<br>
mmrprodemeastor.blob.core.windows.net<br>
mmrprodnoamiot.azure-devices.net<br>
mmrprodnoamstor.blob.core.windows.net

## <a name="enrollment-process"></a>Proceso de inscripción

El proceso de inscripción implica estos pasos:

1. En la barra de navegación izquierda de la Salas de Microsoft Teams – Portal de servicios administrados [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/), expanda **Configuración** y seleccione **General**.
1. En *Inscribir una sala*, seleccione **Descargar instalador**  para descargar el software del agente de supervisión.
1. **Opcional:** Establecer la configuración de proxy para el agente; consulte [Agregar configuración de proxy (opcional).](#adding-proxy-settings-optional)
1. Instale el instalador del agente (descargado en el paso 2) en unidades MTR, ya sea ejecutando el MSI localmente en un dispositivo MTR o a través de sus medios normales de publicación de aplicaciones MSI en conjunto en dispositivos dentro de su entorno (directiva de grupo, etc.).
1. La sala aparece en el portal en un plazo de 5 a 10 minutos. Si no es así, ponte en contacto con managedroomsupport@microsoft.com.

   ![Captura de pantalla de la configuración y las claves de autoinscripción.](../media/software-installation-005new.png)

> [!NOTE]
> Si necesita instalar el agente sin que la aplicación de Teams en MTR pueda iniciar sesión en Teams, puede usar nuestra clave de inscripción como un proceso opcional. Ve a '?'  (Ayuda) en la esquina superior derecha del portal y, a continuación, selecciona 'Clave de descarga (opcional)'. Al instalar el agente, coloque la "clave de autoinscripción" (descargada previamente desde el portal) en el directorio **C:\Rigel** del dispositivo.

## <a name="installation"></a>Instalación

Después de descargar el instalador desde Microsoft (ya sea desde el portal o mediante la dirección URL AKA.ms proporcionada anteriormente), descomprima su contenido para acceder al archivo **ManagedRoomsInstaller.msi**.

Hay dos modos de instalación: 1) instalación de máquina local individual y 2) modo de implementación en masa (normalmente a través de una directiva de grupo de método similar). Se recomienda realizar una instalación individual para equipos que no están unidos a un dominio o para equipos que no tiene ninguna forma de ejecutar instaladores MSI de forma remota.

Debido a las diversas maneras en que los clientes pueden ejecutar aplicaciones MSI en el modo de implementación masiva, este documento solo avanza a través de la instalación en modo individual.

## <a name="individual-devicemdashdomain-joined-walkthrough"></a>&mdash;Tutorial de dispositivos individuales unidos a dominios

1. Inicia sesión en el dispositivo como administrador. Asegúrese de que se siguen *las operaciones en ejecución como el usuario Administración de los pasos del dispositivo*.

1. Copie el **ManagedRoomsInstaller.msi** de archivo en el dispositivo MTR.

   Al ejecutar la ***ManagedRoomsInstaller.msi*** aparece la pantalla Contrato de licencia.

1. Después de leer el contrato, marque ***Acepto los términos del Contrato de licencia** _ y presione _*Install**.

    Se iniciará la instalación del software de supervisión Salas de Microsoft Teams: Servicios administrados. Se muestra una petición de elevación (ejecutar como administrador).

1. Seleccione **Sí**.

    La instalación continuará. Durante el procedimiento de instalación, se abre una ventana de consola e inicia la fase final de la instalación de software de supervisión de Salas de Microsoft Teams: Servicios administrados.

    > [!NOTE]
    > No cierres la ventana. Una vez completada la instalación, el asistente muestra un botón "Finalizar".

## <a name="completing-enrollment"></a>Completar la inscripción

Una vez completada la instalación, espere de 5 a 10 minutos y actualice el portal y se mostrará el dispositivo, que se ha notificado como estado *de incorporación* .

En *el estado de incorporación* , se muestra y se actualiza el estado de la sala, pero no se generan alertas ni se crean solicitudes de investigación.

Elija la sala y seleccione **Inscribirse**  para empezar a recibir alertas de incidentes, incidencias de investigación o para informar de un incidente.

Para cualquier pregunta o problema, abre un incidente notificado por un cliente en el portal o ponte en contacto con managedroomsupport@microsoft.com.

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>Anular la inscripción y desinstalación de software de supervisión

Para anular la inscripción del dispositivo, quite el agente de supervisión del dispositivo MTR de la siguiente manera:

1. En el dispositivo supervisado, inicia sesión en el dispositivo como administrador. Asegúrese de seguir los pasos de *Realizar operaciones como el usuario Administración del dispositivo*.
1. Descargue el script de restablecimiento desde [aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding).
1. Extraiga el script en alguna parte del dispositivo y copie la ruta de acceso.
1. Abra PowerShell como administrador: en la Windows campo ***Search** _ (sección inferior izquierda de la pantalla), escriba "Powershell" y haga clic con el botón derecho en _*_Windows PowerShell_**.
1. Selecciona *"Ejecutar como administrador"* y acepta el mensaje de UAC.
1. Escribe *Set-ExecutionPolicy –ExecutionPolicy RemoteSigned* y, a continuación, presiona **Y** en el siguiente aviso.
1. Pegue o escriba la ruta de acceso completa al script de retirada descomprimido en la ventana de PowerShell y presione **Entrar**.

   Ejemplo:

   ```powershell
   C:\Users\admin\Downloads\MTRP\_Device\_Offboarding\MTRP\_Device\_Offboarding.ps1
   ```

   Este comando restablece el dispositivo a las actualizaciones estándar de MTR del usuario y quita el agente de supervisión MTRP y los archivos.

1. En el menú de la izquierda de la Salas de Microsoft Teams - Portal de servicios administrados, seleccione **Salas**.
1. En la lista de salas proporcionada, elija la sala que desea anular la inscripción y seleccione **Anular la inscripción** para dejar de recibir alertas de incidentes o incidencias de investigación, o para informar de un incidente para la sala.

## <a name="troubleshooting-table"></a>Tabla de solución de problemas

> [!NOTE]
> Todos los Salas de Microsoft Teams: los errores de supervisión de servicios administrados se registran en un archivo de registro de eventos específico denominado **Salas administradas de Microsoft**.

***Ubicación del archivo de registro en tiempo de ejecución de la aplicación*** =

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortal\_Verbose\_LogFile.log, donde **x.x.x** es el número de versión de la aplicación.

|Síntoma|Procedimiento recomendado|
|---|---|
|Recibe un mensaje de error que indica: </p><p> ***ERROR: Ejecute esta aplicación con** _ <br> _ *_privilegios elevados_**|Ejecute la aplicación con privilegios escalados y vuelva a intentarlo.|
|||
|Recibe un mensaje de error que indica: </p><p> ***No se pueden encontrar datos tpm***|Asegúrate de que el dispositivo tenga activado TPM (Módulo de plataforma segura) en su BIOS. Esto suele encontrarse en la configuración de seguridad del BIOS del dispositivo.|
|||
|Recibe un mensaje de error: </p><p> ***ERROR: No se encuentra la cuenta de usuario local denominada "Administración" o "Skype".***|Asegúrese de que las cuentas de usuario existen en el dispositivo certificado Microsoft Teams Room systems.|
|||
|Recibirá los mensajes de estado de error que no se incluyan anteriormente.|Facilita una copia del registro de instalación al agente de soporte técnico de Microsoft Teams System.|
