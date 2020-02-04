---
title: Migrar la configuración de la aplicación de estacionamiento de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba55ec7ff54858d3324df2ab8794176a5dc7a10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a>Migrar la configuración de la aplicación de estacionamiento de llamadas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

La migración de la aplicación de estacionamiento de llamadas de Lync Server 2010 a Lync Server 2013 incluye el aprovisionamiento del grupo de Lync Server 2013 con cualquier música personalizada que contenga archivos que se hayan cargado en Lync Server 2010, restaurando la configuración del nivel de servicio y redestinando todas las llamadas en órbita a la agrupación de Lync Server 2013. Si se han configurado archivos de música en espera personalizados en el grupo de servidores de Lync Server 2010, estos archivos deben copiarse en el nuevo grupo de Lync Server 2013. Además, se recomienda que haga una copia de seguridad de todos los archivos de música en espera personalizados de Lync Server 2010 a otro destino para mantener una copia de seguridad separada de los archivos de música personalizada que se han cargado para la llamada en espera. Los archivos de música personalizada habilitada para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo. Para copiar los archivos de audio de un almacenamiento de archivos del grupo de servidores de Lync Server 2010 en un almacén de archivos de Lync Server 2013, use el comando **xcopy** con los siguientes parámetros:

   ```
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

Cuando todos los archivos de audio personalizados se han copiado en el almacén de archivos de Lync Server 2013, se debe configurar la configuración de la aplicación de estacionamiento de llamadas del grupo de Lync Server 2013, y los intervalos de la órbita de la llamada de estacionamiento que están asociados con el grupo de Lync Server 2010 se deben reasignar a el grupo de 2013 de Lync Server.

La configuración de la aplicación estacionamiento de llamadas incluye el umbral de tiempo de espera de recogida, la habilitación o deshabilitación de música en espera, los intentos de recopilación de llamadas máximas y la solicitud de tiempo de espera. Debe administrar la configuración de la aplicación de estacionamiento de llamadas con el shell de administración de Lync Server para ejecutar el cmdlet **set-CsCpsConfiguration** . La configuración de la aplicación estacionamiento de llamadas no se puede administrar con el panel de control de Lync Server.

**Cambiar la configuración del servicio de estacionamiento de llamadas**

1.  En el servidor front-end de Lync Server 2013, abra el shell de administración de Lync Server.

2.  En la línea de comandos, escriba:
    
    <div>
    

    > [!NOTE]  
    > Si la configuración de la aplicación de Lync Server 2013 es idéntica a la configuración heredada de Lync Server 2010, puede omitir la ejecución de este paso. Si la configuración de la aplicación de estacionamiento de llamadas es diferente para los entornos Lync Server 2013 y Lync Server 2010, use el cmdlet que se muestra a continuación como una plantilla para actualizar esos cambios.

    
    </div>
    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

Para reasignar todos los intervalos orbitar de llamadas de Lync Server 2010 al grupo de servidores de Lync Server 2013, puede usar el panel de control de Lync Server o el shell de administración de Lync Server.

**Reasignar todos los intervalos orbital de la llamada de estacionamiento con el panel de control de Lync Server**

1.  Abra el Panel de control de Lync Server.

2.  En el panel izquierdo, seleccione **características de voz**.

3.  Seleccione la pestaña **detener llamada** .

4.  Para cada rango de la órbita de la llamada que se asigna a un grupo de 2010 de Lync Server, edite el FQDN de la configuración del **servidor de destino** y seleccione el grupo de lync Server 2013 que procesará las solicitudes de estacionamiento de llamada.

5.  Seleccione **confirmar** para guardar los cambios.

**Reasignar todos los intervalos órbitas del parque de llamadas con el shell de administración de Lync Server**

1.  Abra el Shell de administración de Lync Server.

2.  En la línea de comandos, escriba:
    
        Get-CsCallParkOrbit
    
    Este cmdlet muestra todos los intervalos de la órbita de estacionamiento de llamadas en la implementación. Todas las órbitas de estacionamiento de llamadas que tienen los parámetros **CallParkServiceId** y **CallParkServerFqdn** establecidos como el grupo de Lync Server 2010 deben reasignarse.
    
    Para reasignar los intervalos orbitar de Lync Server 2010 a la cola de Lync Server 2013, en la línea de comandos, escriba lo siguiente:
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

Después de reasignar todos los intervalos orbitar de llamadas al grupo de Lync Server 2013, se completará el proceso de migración de la aplicación de estacionamiento de llamadas y el grupo de Lync Server 2013 administrará todas las solicitudes de estacionamiento de llamadas futuras.

</div>

<span> </span>

</div>

</div>

</div>

