---
title: Inscribir un dispositivo Teams room en Servicios administrados
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
description: Incorporación de Salas de Teams dispositivos a servicios administrados
f1keywords: ''
ms.openlocfilehash: 4261e93a7bfab5d21620f8dbb327575352062c86
ms.sourcegitcommit: abe942c294ed5fca70efdf039d38d611b9c21fe9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2022
ms.locfileid: "63689196"
---
# <a name="enroll-device-into-managed-service"></a>Inscribir el dispositivo en el servicio administrado

La implementación requiere la incorporación Salas de Microsoft Teams dispositivos a los Salas de Microsoft Teams servicios administrados. El agente de servicio de supervisión se usa con sistemas Microsoft Teams y periféricos de sala de almacenamiento (MTR) certificados.

## <a name="prerequisites"></a>Requisitos previos

Siga estos procedimientos para configurar el hardware antes de intentar el proceso de inscripción:

### <a name="adding-proxy-settings-optional"></a>Agregar configuración de proxy (opcional)

1. Inicie sesión como administrador siguiendo [las operaciones realizadas como usuario administrador del dispositivo MTR](#performing-operations-as-the-admin-user-of-the-mtr-device).
1. En el Windows campo ***Search** _ (sección inferior izquierda de la pantalla), escriba _ *cmd** (presione larga la pantalla o seleccione la derecha y elija Ejecutar como **_administrador_**).  
1. Ejecute el siguiente comando (las comillas dobles al final del comando son importantes):
   - Si usa un único ***servidor proxy***: bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY <proxyserver>:<port> ""

      *Ejemplo:* bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY contosoproxy.corp.net:8080 ""
      

   - Si usa un ***archivo pac*** : bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url>

      
      *Ejemplo:* bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT `http://contosoproxy.corp.net/proxy.pac`
      

### <a name="enabling-tpm-settings"></a>Habilitar la configuración de TPM

> [!NOTE]
> Tpm debe estar habilitado para inscribirse en el servicio administrado.

Si TPM en un dispositivo Intel NUC está deshabilitado, habilite TPM en estos dispositivos de la siguiente manera:  

1. Conecta el teclado a un dispositivo NUC.  
1. Reiniciar dispositivo.  
1. Para mostrar la pantalla del BIOS, presione **F2 rápidamente**.  
1. Seleccione **Avanzadas**.  
1. Seleccione **Seguridad**.  
1. En el lado derecho, debajo de Características de seguridad, habilite **la tecnología intel platform trust**.  
1. Para guardar la configuración, presione **F10**.  
1. En el cuadro de confirmación, seleccione **Sí**. 
## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>Realizar operaciones como usuario administrador del dispositivo MTR

Algunos procedimientos de configuración e instalación requieren que inicie sesión en el dispositivo como administrador.

Para iniciar sesión en el dispositivo como administrador (administrador local):

1. Asegúrese de colgar las llamadas en curso y volver a la pantalla principal.
1. En la interfaz Microsoft Teams usuario del salón, seleccione Más y, a continuación, seleccione **Configuración**, donde se le pedirá la contraseña de administrador local en el dispositivo (la contraseña predeterminada es **_sfb_**).
1. Seleccione **Configuración** y, a continuación **, seleccione Windows Configuración** para acceder a Windows como administrador local.  

1. En la lista de usuarios que se muestran en la Windows de inicio de sesión, seleccione **Administrador (o** el administrador local correspondiente del dispositivo).

> [!NOTE]
> Si el equipo está unido *al* dominio, elija **Otro** usuario y, a continuación, use **.\admin** o el nombre de usuario del administrador local configurado en el dispositivo como nombre de usuario.  

Para volver a la aplicación Microsoft Teams room después de realizar las tareas administrativas necesarias:

1. En el Windows ***menú Inicio***, cerrar sesión desde la cuenta de administrador.
1. Vuelva a Microsoft Teams sala seleccionando el icono de cuenta de usuario en el lado izquierdo de la pantalla y, a continuación **, seleccionando Skype**.

> [!NOTE]
> Si el Skype usuario no aparece en la lista, seleccione Otro usuario, escriba ***.\skype*** como nombre de usuario e inicie sesión.

 

## <a name="urls-required-for-communication"></a>Direcciones URL necesarias para la comunicación

 > [!NOTE]
 > Todo el tráfico de red entre el agente de dispositivos MTR y Salas de Microsoft Teams: el portal de servicios administrados es SSL a través del puerto 443 *.*  Vea [Office 365 direcciones URL e intervalos de direcciones IP : Microsoft 365 Enterprise | Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

Los siguientes hosts deben permitirse si tiene habilitada la **lista de permitidos de tráfico** dentro de su entorno empresarial:

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

El proceso de inscripción incluye estos pasos:  

1. En la barra de navegación izquierda del portal [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/)Salas de Microsoft Teams: Servicios administrados, expanda **Configuración** y seleccione **General**.  
1. En *Inscribir un salón*, seleccione **Descargar instalador**  para descargar el software del agente de supervisión.
1. **Opcional:** Configurar la configuración de proxy para el agente; vea [Agregar configuración de proxy (opcional).](#adding-proxy-settings-optional).
1. Instale el instalador del agente (descargado en el paso 2) en unidades MTR, ya sea ejecutando el MSI localmente en un dispositivo MTR o a través de sus medios normales de publicación de aplicaciones MSI en masa en dispositivos dentro de su entorno (directiva de grupo, etc.).  
1. La sala aparece en el portal en un plazo de 5 a 10 minutos. Si no es así, póngase en contacto managedroomsupport@microsoft.com.  

   ![Captura de pantalla de la configuración y las claves de autoinscripción.](../media/software-installation-005new.png)
 
> [!NOTE]
> Si necesita instalar el agente sin que la aplicación Teams en el MTR pueda iniciar sesión en Teams, puede usar nuestra clave de inscripción como un proceso opcional. Vaya a '?'  (Ayuda) en la esquina superior derecha del portal y, a continuación, seleccione "Tecla Descargar (opcional)". Al instalar el agente, coloque la "Clave de autoinscripción" (descargada previamente desde el portal) en el  **C:\Rigeldirectory**  del dispositivo.

## <a name="installation"></a>Instalación

Después de descargar el instalador de Microsoft (ya sea desde el portal o mediante la dirección URL de AKA.ms proporcionada anteriormente), descomprima su contenido para obtener acceso al archivo **ManagedRoomsInstaller.msi.**

Hay dos modos de instalación: 1) modo de instalación local individual y 2) modo de implementación masiva (normalmente a través de una directiva de grupo de método similar). Se recomienda la instalación individual para equipos que no están unidos a un dominio o para equipos que no tiene ninguna forma de ejecutar instaladores MSI de forma remota.  

Debido a las diversas formas en que los clientes pueden ejecutar aplicaciones MSI en modo de implementación masiva, este documento solo explica la instalación en modo individual.  
## <a name="individual-devicemdashdomain-joined-walkthrough"></a>Tutorial individual unido a DeviceDomain&mdash;

1. Inicie sesión en el dispositivo como administrador. Asegúrese de *realizar las operaciones como usuario administrador de los pasos del* dispositivo.

1. Copie el archivo **ManagedRoomsInstaller.msi** al dispositivo MTR.

   Al ejecutar la ***ManagedRoomsInstaller.msi*** es una pantalla contrato de licencia.

1.  Después de leer el contrato, compruebe ***Acepto los** términos del Contrato de licencia_ y presione _*Instalar**.  

    Comienza la instalación Salas de Microsoft Teams software de supervisión de servicios administrados. Se muestra una solicitud de elevación (ejecutar como administrador).

 1. Seleccione **Sí**.

    La instalación continuará. Durante el procedimiento de instalación, se abre una ventana de consola y comienza la fase final de la Salas de Microsoft Teams: instalación de software de supervisión de servicios administrados.  

    > [!NOTE]
    > No cierre la ventana. Una vez completada la instalación, el asistente muestra el botón "Finalizar".

## <a name="completing-enrollment"></a>Completar la inscripción

Una vez completada la instalación, espere entre 5 y 10 minutos y actualice el portal y el dispositivo aparecerá en la lista, notificado como *estado de* incorporación.

En *el estado de* incorporación, el estado de la sala se muestra y actualiza, pero no genera alertas ni crea vales de investigación.

Elija el salón y seleccione **Inscribirse**  para empezar a recibir alertas de incidentes, incidencias de investigación o para informar de un incidente.

Para cualquier pregunta o problema, abra un incidente notificado por un cliente en el portal o póngase en contacto con managedroomsupport@microsoft.com.

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>Desanrollar y desinstalar software de supervisión

Para desenrollar el dispositivo, quite el agente de supervisión del dispositivo MTR de la siguiente manera:

1. En el dispositivo que se está supervisando, inicie sesión en el dispositivo como administrador. Asegúrese de seguir los pasos de *Realizar operaciones como usuario administrador del dispositivo*.
1. Descargue el script de restablecimiento [desde aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding).
1. Extraiga el script en algún lugar del dispositivo y copie la ruta de acceso.
1. Abra PowerShell como administrador: en el campo Windows ***Search** _ (sección inferior izquierda de la pantalla), escriba "Powershell" y haga clic con el botón derecho en _*_Windows PowerShell_**.
1. Seleccione *"Ejecutar como administrador"* y acepte el mensaje de UAC.
1. Escriba *Set-ExecutionPolicy –ExecutionPolicy RemoteSigned* y, a continuación, presione **Y** en el siguiente mensaje.  
1. Pegue o escriba la ruta completa del script de offboarding descomprimido en la ventana de PowerShell y presione **Entrar**.

   Ejemplo:

   *C:\Usuarios\administrador\Descargas\MTRPDeviceOffboarding\_\_\MTRPDevice\_\_Offboarding.ps1*  

   De este modo, se restablece el dispositivo a las actualizaciones estándar de MTR del usuario y se quitan los archivos y el agente de supervisión MTRP.

1. En el menú izquierdo del portal Salas de Microsoft Teams servicios administrados, seleccione **Salas**.  
1. En la lista de salas proporcionadas, elija la sala que desea desanrollar y seleccione **Desanrollar** para dejar de recibir alertas de incidentes o incidencias de investigación, o para informar de un incidente para la sala.

## <a name="troubleshooting-table"></a>Tabla de solución de problemas

> [!NOTE]
> Todas Salas de Microsoft Teams: los errores de supervisión de los servicios administrados se registran en un archivo de registro de eventos específico denominado **Salas administradas de Microsoft**. 

### <a name="application-runtime-log-file-location-"></a>***Ubicación del archivo de registro en tiempo de ejecución de la aplicación*** =  

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortalVerboseLogFile.log\_\_, donde **x.x.x** es el número de versión de la aplicación.

|**Síntoma**  |**Procedimiento recomendado**  |
| :- | :- |
|<p>Recibe un mensaje de error que indica   </p><p>***ERROR: Ejecute esta aplicación con** _ </p><p>Privilegios _ *_elevated_**  </p>|Ejecutar la aplicación con privilegios escalados e intentarlo de nuevo  |
|  |  |
|<p>Recibe un mensaje de error que indica   </p><p>***No se pueden encontrar datos de TPM***  </p>|Asegúrese de que el dispositivo tiene TPM (Módulo de plataforma de confianza) activado en su BIOS. Esto suele encontrarse en la configuración de seguridad del BIOS del dispositivo  |
|  |  |
|<p>Recibe un mensaje de error  </p><p>` `***ERROR: No se encuentra la cuenta de usuario local denominada "Administrador" o "Skype"***  </p>|Asegúrese de que las cuentas de usuario existen en el dispositivo Microsoft Teams de sistemas room certificados.  |
|  |  |
|Recibe los mensajes de estado de error que no se tratan anteriormente  |Proporcione una copia del registro de instalación a su Microsoft Teams de soporte técnico del sistema. |
