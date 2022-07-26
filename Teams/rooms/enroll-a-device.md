---
title: Inscribir un dispositivo de sala de Teams en Servicios administrados
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 07/22/2022
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
ms.openlocfilehash: 124d301a37fde8802b60f3e59ad5f1a1dd19862c
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005440"
---
# <a name="enroll-device-into-managed-service"></a>Inscribir el dispositivo en un servicio administrado

La implementación requiere la incorporación Salas de Microsoft Teams dispositivos a los servicios administrados Salas de Microsoft Teams. El agente de servicio de supervisión se usa con sistemas y periféricos certificados de Microsoft Teams Room (MTR).

## <a name="prerequisites"></a>Requisitos previos

Sigue estos procedimientos para configurar el hardware antes de intentar el proceso de inscripción:

### <a name="adding-proxy-settings-optional"></a>Agregar configuración de proxy (opcional)

1. Inicie sesión como administrador siguiendo [realizando operaciones como el usuario Administración del dispositivo MTR](#performing-operations-as-the-admin-user-of-the-mtr-device).
1. En el campo Windows ***Search** _ (sección inferior izquierda de la pantalla), escribe _ *cmd** (mantén presionada la pantalla o selecciona la derecha y elige **_Ejecutar como administrador_**).
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
1. En la interfaz de usuario de sala de Microsoft Teams, seleccione  **Más** y, a continuación, seleccione **Configuración**, donde se le pedirá la contraseña de administrador local en el dispositivo (la contraseña predeterminada es **_sfb_**).
1. Selecciona **Configuración** y, a continuación, selecciona  **Configuración de Windows**  para acceder a Windows como administrador local.

1. En la lista de usuarios que se muestra en la pantalla de inicio de sesión de Windows, selecciona  **Administrador** (o el correspondiente administrador local del dispositivo).

> [!NOTE]
> Si el equipo está *unido a un dominio*, elige **Otro usuario** y, a continuación, usa **.\admin** o el nombre de usuario del administrador local configurado en el dispositivo como nombre de usuario.

Para volver a la aplicación Salas de Microsoft Teams después de realizar las tareas administrativas necesarias:

1. En el ***menú Inicio*** de Windows, cierra sesión en la cuenta de Administración.
1. Para volver a Salas de Microsoft Teams, selecciona el icono de cuenta de usuario en el extremo izquierdo de la pantalla y, a continuación, selecciona **Skype**.

> [!NOTE]
> Si el usuario de Skype no aparece en la lista, seleccione Otro usuario, escriba ***.\skype*** como el nombre de usuario e inicie sesión.

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

1. En la barra de navegación izquierda de la Salas de Microsoft Teams - Portal de servicios administrados [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/), expanda **Configuración** y seleccione **General**.
1. En *Inscribir una sala*, seleccione **Descargar instalador**  para descargar el software del agente de supervisión.
1. **Opcional:** Establecer la configuración de proxy para el agente; consulte [Agregar configuración de proxy (opcional).](#adding-proxy-settings-optional)
1. Instale el instalador del agente (descargado en el paso 2) en unidades MTR, ya sea ejecutando el MSI localmente en un dispositivo MTR o a través de sus medios normales de publicación de aplicaciones MSI en conjunto en dispositivos dentro de su entorno (directiva de grupo, etc.).
1. La sala aparece en el portal en un plazo de 5 a 10 minutos. Si no es así, ponte en contacto con managedroomsupport@microsoft.com.

   ![Captura de pantalla de la configuración y las claves de autoinscripción.](../media/software-installation-005new.png)

> [!NOTE]
> Si necesita instalar el agente sin que la aplicación de Teams en MTR pueda iniciar sesión en Teams, puede usar nuestra clave de inscripción como un proceso opcional. Ve a '?'  (Ayuda) en la esquina superior derecha del portal y, a continuación, selecciona 'Clave de descarga (opcional)'. Al instalar el agente, coloque la "clave de autoinscripción" (descargada previamente desde el portal) en el directorio **C:\Rigel** del dispositivo.

## <a name="installation"></a>Instalación

Después de descargar el instalador desde Microsoft (ya sea desde el portal o mediante la dirección URL AKA.ms proporcionada anteriormente), descomprima su contenido para acceder al archivo **ManagedRoomsInstaller.msi**.

Hay dos modos de instalación: 1) instalación de máquina local individual y 2) modo de implementación en masa (normalmente a través de Intune de método similar). Se recomienda realizar una instalación individual para equipos que no están unidos a un dominio o para equipos que no tiene ninguna forma de ejecutar instaladores MSI de forma remota.

Debido a las diversas formas en que los clientes pueden ejecutar aplicaciones MSI en el modo de implementación en masa, este documento muestra solo la instalación en modo individual, así como de forma masiva en dispositivos inscritos en Intune.

### <a name="individual-device-installation"></a>Instalación de dispositivos individuales

1. Inicia sesión en el dispositivo como administrador. Asegúrese de que se siguen *las operaciones en ejecución como el usuario Administración de los pasos del dispositivo*.

1. Copie el **ManagedRoomsInstaller.msi** de archivo en el dispositivo MTR.

   Al ejecutar la ***ManagedRoomsInstaller.msi*** aparece la pantalla Contrato de licencia.

1. Después de leer el contrato, marque ***Acepto los términos del Contrato de licencia** _ y presione _*Install**.

    Se iniciará la instalación del software de supervisión Salas de Microsoft Teams: Servicios administrados. Se muestra una petición de elevación (ejecutar como administrador).

1. Seleccione **Sí**.

    La instalación continuará. Durante el procedimiento de instalación, se abre una ventana de consola e inicia la fase final de la instalación de software de supervisión de Salas de Microsoft Teams: Servicios administrados.

    > [!NOTE]
    > No cierres la ventana. Una vez completada la instalación, el asistente muestra un botón "Finalizar".

### <a name="intune-enrolled-device-bulk-deployment"></a>Implementación masiva de dispositivos inscritos en Intune

Los siguientes componentes son requisitos previos para una instalación correcta: 

- **Intune inscripción**: Salas de Teams en dispositivos Windows ya debe estar inscrito en Intune.
  Para obtener más información sobre cómo inscribir Salas de Teams en dispositivos Windows en Intune, consulta [Inscribir Salas de Microsoft Teams en dispositivos Windows con Microsoft Endpoint Manager: Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- **Grupo de Azure AD con todos los Salas de Teams en dispositivos Windows como miembros**: un grupo creado en Azure AD que incluye todos los Salas de Teams en dispositivos Windows que deben formar parte del servicio Salas de Microsoft Teams Premium. Este grupo se usará para dirigir la implementación del agente MTRP.
  
> [!NOTE]
> Puede usar grupos dinámicos en Azure AD para este fin, más información en [Inscribir Salas de Microsoft Teams en dispositivos Windows con Microsoft Endpoint Manager: Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- Descargar **el instalador** del **agente MTRP**: descargue el archivo zip del agente y <https://aka.ms/serviceportalagentmsi> extraiga el contenido del archivo zip (ManagedRoomsInstaller.msi) en una carpeta temporal local.

**Para instalar con Intune**

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
1. Selecciona **Aplicaciones** > **Agregar todas las aplicaciones** > **.**
1. En el panel **Seleccionar tipo de aplicación** , en **Otros** tipos de aplicación, seleccione **Aplicación de línea de negocio**.
1. Haga clic en **Seleccionar**. Se muestran los pasos **agregar aplicación** . 
1. En el panel **Agregar aplicación** , haz clic en **Seleccionar archivo de paquete de la aplicación**.
   1. En el panel **Archivo de paquete** de la aplicación, selecciona  **Examinar**. A continuación, seleccione el archivo **ManagedRoomsInstaller.msi** descargado previamente (consulte la sección requisitos previos).
   1. Cuando hayas terminado, selecciona **Aceptar** en el panel **Archivo de paquete** de la aplicación para agregar la aplicación.
1. En la página **Información de la aplicación** , realice los cambios siguientes:
   1. Editor: escriba **Microsoft Corporation**.
   1. Omitir la versión de la aplicación: selecciona **Sí**.

      > [!NOTE]
      > El agente MTRP se está actualizando; por lo tanto, debe ignorar explícitamente la versión de la aplicación (cualquier versión de línea base puede actualizarse automáticamente).

   1. (Opcional) Categoría: seleccione **Administración de equipos**.
   
1. Haga clic en **Siguiente** para mostrar la página **Tareas** .
   1. En la sección **Requerido** , haga clic en **+ agregar grupo** para dirigirse a un grupo de dispositivos para la instalación del agente.
   1. En el panel **Seleccionar grupo** , escriba el nombre del grupo en el cuadro de búsqueda (consulte los requisitos previos anteriores) y haga clic en el **grupo** que desee y haga clic en **Seleccionar**.
      Para obtener más información, vea [Agregar grupos para organizar usuarios y dispositivos](https://go.microsoft.com/fwlink/?linkid=2202166) y [Asignar aplicaciones a grupos con Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2202270).
1. Haga clic en **Siguiente** para mostrar la página **Revisar y crear** .
1. Revise los valores y la configuración que especificó para la aplicación. Cuando haya terminado, haga clic en **Crear** para agregar la aplicación a Intune.

Una vez completado el proceso, los dispositivos empezarán a instalar el agente MTRP pasados unos minutos.

> [!NOTE]
> Después de la instalación, el agente MTRP puede tardar hasta ocho horas en ejecutar una actualización automática de la versión más reciente y aparecer en el portal de MTRP.
Para acelerar la inscripción automática en el portal de MTRP, considere la posibilidad de reiniciar el dispositivo MTR después de la implementación del agente.

## <a name="completing-enrollment"></a>Completar la inscripción

Una vez completada la instalación, espere de 5 a 10 minutos y, a continuación, actualice el portal para ver el dispositivo en la lista, que se ha notificado como estado *de incorporación* .

En *el estado de incorporación* , se muestra y se actualiza el estado de la sala, pero no se generan alertas ni se crean solicitudes de investigación.

Elija la sala y seleccione **Inscribirse**  para empezar a recibir alertas de incidentes, incidencias de investigación o para informar de un incidente.

Para cualquier pregunta o problema, abre un incidente notificado por el cliente en el portal o ponte en contacto con managedroomsupport@microsoft.com.

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>Anular la inscripción y desinstalación de software de supervisión

Para anular la inscripción del dispositivo, quite el agente de supervisión del dispositivo MTR de la siguiente manera:

1. En el dispositivo supervisado, inicia sesión en el dispositivo como administrador. Asegúrese de seguir los pasos de *Realizar operaciones como el usuario Administración del dispositivo*.
1. Descargue el script de restablecimiento desde [aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding).
1. Extraiga el script en alguna parte del dispositivo y copie la ruta de acceso.
1. Abra PowerShell como administrador: en el campo Windows ***Search** _ (sección inferior izquierda de la pantalla), escriba "Powershell" y haga clic con el botón derecho en _*_Windows PowerShell_**.
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
|Recibe un mensaje de error: </p><p> ***ERROR: No se encuentra la cuenta de usuario local denominada 'Administración' o 'Skype'***|Asegúrese de que las cuentas de usuario existen en el dispositivo certificado de sistemas de salas de Microsoft Teams.|
|||
|Recibirá los mensajes de estado de error que no se incluyan anteriormente.|Proporcione una copia del registro de instalación al agente de soporte técnico de Microsoft Teams System.|
