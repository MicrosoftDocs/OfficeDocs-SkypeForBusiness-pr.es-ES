---
title: Migrar la configuración de la aplicación de estacionamiento de llamadas
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63b91c6a742310d14031bdadc28cbc6ca57e115
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503567"
---
# <a name="migrate-call-park-application-settings"></a>Migrar la configuración de la aplicación de estacionamiento de llamadas

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

La migración de la aplicación de estacionamiento de llamadas de Lync Server 2010 a Lync Server 2013 incluye el aprovisionamiento del grupo de Lync Server 2013 con cualquier archivo de música personalizado en retención que se haya cargado en Lync Server 2010, restaurando la configuración del nivel de servicio y redestinando todas las órbitas de estacionamiento de llamadas al grupo de Lync Server 2013. Si se han configurado archivos de música en espera personalizados en el grupo de servidores de Lync Server 2010, estos archivos deben copiarse en el nuevo grupo de servidores de Lync Server 2013. Además, se recomienda realizar una copia de seguridad de los archivos de música en espera personalizados de la música en espera de Lync Server 2010 en otro destino para mantener una copia de seguridad independiente de los archivos de música en espera personalizados que se han cargado para el estacionamiento de llamadas. Los archivos de música en espera personalizados para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo de servidores. Para copiar los archivos de audio de un almacén de archivos de un grupo de servidores de Lync Server 2010 en un almacén de archivos de Lync Server 2013, use el comando **xcopy** con los siguientes parámetros:

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

Cuando todos los archivos de audio personalizados se han copiado en el almacén de archivos de Lync Server 2013, la configuración de la aplicación de estacionamiento de llamadas del grupo de Lync Server 2013 debe configurarse, y los intervalos de órbita de estacionamiento de llamadas asociados con el grupo de Lync Server 2010 deben reasignarse al grupo de servidores de Lync Server 2013.

Los valores de aplicación de estacionamiento de llamadas incluyen el umbral de tiempo de espera de recogida, la habilitación o deshabilitación de la música en espera, los intentos de recogida de llamadas máximos y la solicitud de tiempo de espera. Debe administrar la configuración de la aplicación de estacionamiento de llamadas mediante el shell de administración de Lync Server para ejecutar el cmdlet **set-CsCpsConfiguration** . No se puede administrar la configuración de la aplicación estacionamiento de llamadas mediante el panel de control de Lync Server.

**Volver a configurar los valores de servicio de estacionamiento de llamadas**

1.  En el servidor front-end de Lync Server 2013, abra el shell de administración de Lync Server.

2.  Escriba lo siguiente en la línea de comandos:
    
    <div>
    

    > [!NOTE]  
    > Si la configuración de la aplicación de estacionamiento de llamadas de Lync Server 2013 es idéntica a la configuración heredada de Lync Server 2010, puede omitir este paso. Si la configuración de la aplicación estacionamiento de llamadas es diferente para los entornos Lync Server 2013 y Lync Server 2010, use el cmdlet siguiente como plantilla para actualizar dichos cambios.

    
    </div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-EnableMusicOnHold" <LS2010 CPS value> "-MaxCallPickupAttempts" <LS2010 CPS pickup attempts> "-OnTimeoutURI" <LS2010 CPS timeout URI> " ```

Para reasignar todos los intervalos de órbitas de estacionamiento de llamadas del grupo de servidores de Lync Server 2010 al grupo de Lync Server 2013, puede usar el panel de control de Lync Server o el shell de administración de Lync Server.

**Reasignar todos los intervalos de órbitas de estacionamiento de llamadas mediante el panel de control de Lync Server**

1.  Abra Panel de control de Lync Server

2.  En el panel izquierdo, seleccione **Características de voz**.

3.  Seleccione la pestaña **Estacionamiento de llamadas**.

4.  Para cada intervalo de órbitas de estacionamiento de llamadas asignado a un grupo de servidores de Lync Server 2010, edite el FQDN de la configuración del **servidor de destino** y seleccione el grupo de lync Server 2013 que procesará las solicitudes de estacionamiento de llamadas.

5.  Seleccione **Confirmar** para guardar los cambios.

**Vuelva a asignar todos los intervalos de órbita de estacionamiento de llamadas mediante el Shell de administración de Lync Server**

1.  Abra el shell de administración de Lync Server.

2.  En la línea de comandos, escriba lo siguiente:
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    Este cmdlet muestra todos los intervalos de órbita de estacionamiento de llamadas de la implementación. Todas las órbitas de estacionamiento de llamadas que tienen los parámetros **CallParkServiceId** y **CallParkServerFqdn** establecidos como grupo de Lync Server 2010 deben reasignarse.
    
    Para reasignar intervalos de órbita de estacionamiento de llamadas de Lync Server 2010 al grupo de servidores de Lync Server 2013, en la línea de comandos, escriba lo siguiente:
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

Después de reasignar todos los intervalos de órbitas de estacionamiento de llamadas al grupo de servidores de Lync Server 2013, se completará el proceso de migración de la aplicación de estacionamiento de llamadas y el grupo de servidores de Lync Server 2013 administrará todas las solicitudes de estacionamiento de llamadas futuras.

</div>

<span> </span>

</div>

</div>

</div>

