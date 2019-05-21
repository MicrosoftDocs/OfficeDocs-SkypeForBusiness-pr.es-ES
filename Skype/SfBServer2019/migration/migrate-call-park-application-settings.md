---
title: Migrar la configuración de la aplicación de estacionamiento de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'La migración de la aplicación de estacionamiento de llamadas incluye el aprovisionamiento del grupo de servidores de Skype empresarial 2019 con cualquier música personalizada en los archivos que se hayan cargado en la instalación heredada, la restauración de la configuración del nivel de servicio y la redestinación de todas las opciones de estacionamiento de la Grupo de servidores de Skype empresarial 2019. Si se han configurado archivos de música en espera personalizados en el grupo, estos archivos deben copiarse en el nuevo grupo de servidores de Skype empresarial 2019. Además, se recomienda que haga una copia de seguridad de todos los archivos de música en espera personalizados de la llamada en espera para mantener una copia de seguridad separada de los archivos de música personalizada que se hayan cargado en el parque de llamadas. Los archivos de música personalizada habilitada para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo. Para copiar los archivos de audio de un grupo de almacenamiento de archivos en un almacén de archivos de Skype empresarial Server 2019, use el comando xcopy con los siguientes parámetros:'
ms.openlocfilehash: aa4ac3cfbe6802b8853a8ec8886f8fffe1a20a51
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280835"
---
# <a name="migrate-call-park-application-settings"></a>Migrar la configuración de la aplicación de estacionamiento de llamadas

La migración de la aplicación de estacionamiento de llamadas incluye el aprovisionamiento del grupo de servidores de Skype empresarial 2019 con cualquier archivo de música personalizada que se haya cargado en la instalación heredada, la restauración de la configuración de nivel de servicio y la redestinación de todas las órbitas de estacionamiento de llamadas al grupo de servidores de Skype empresarial 2019. Si se han configurado archivos de música en espera personalizados en el grupo, estos archivos deben copiarse en el nuevo grupo de servidores de Skype empresarial 2019. Además, le recomendamos que haga una copia de seguridad de los archivos de música en espera personalizados de un parque a otro destino para mantener una copia de seguridad separada de los archivos de música personalizada que se hayan cargado para la llamada en espera. Los archivos de música personalizada habilitada para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo. Para copiar los archivos de audio de un grupo de almacenamiento de archivos en un almacén de archivos de Skype empresarial Server 2019, use el comando **xcopy** con los siguientes parámetros: 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Cuando todos los archivos de audio personalizados se han copiado en el almacén de archivos de Skype empresarial Server 2019, la configuración de la aplicación estacionamiento de llamadas del grupo de Skype empresarial Server 2019 debe estar configurada y los intervalos de la órbita del parque de llamadas asociados con el grupo heredado. debe reasignarse al grupo de servidores de Skype empresarial 2019.

La configuración de la aplicación estacionamiento de llamadas incluye el umbral de tiempo de espera de la recogida, la habilitación o deshabilitación de música en espera, los intentos de recopilación de llamadas máximas y la solicitud de tiempo de espera. Debe administrar la configuración de la aplicación de estacionamiento de llamadas con el shell de administración de Skype empresarial Server para ejecutar el cmdlet **set-CsCpsConfiguration** . No puede administrar la configuración de la aplicación de estacionamiento de llamadas con el panel de control de Skype empresarial Server. 

## <a name="reconfigure-the-call-park-service-settings"></a>Cambiar la configuración del servicio de estacionamiento de llamadas

1. Desde el servidor front-end de Skype empresarial Server 2019, abra el shell de administración de Skype empresarial Server.

2. En la línea de comandos, escriba:

    > [!NOTE]
    > Si la configuración de la aplicación de Skype para empresas Server 2019 es idéntica a la configuración heredada, puede omitir este paso. Si la configuración de la aplicación de estacionamiento de llamadas es diferente para los entornos de Skype empresarial Server 2019 y los antiguos, use el cmdlet que se muestra a continuación como una plantilla para actualizar esos cambios. 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Para reasignar todos los intervalos de llamadas de la órbita de la agrupación heredada al grupo de servidores de Skype empresarial 2019, puede usar el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Reasignar todos los intervalos órbitas del parque de llamadas con el panel de control de Skype empresarial Server

1. Abra el panel de control de Skype empresarial Server.

2. En el panel izquierdo, seleccione **características de voz**.

3. Seleccione la pestaña **detener llamada** . 

4. Para cada rango de la órbita de la llamada que se asigna a una agrupación heredada, edite el **FQDN del servidor de destino** y seleccione el grupo de servidores de Skype empresarial 2019 que procesarán las solicitudes de estacionamiento. 

5. Seleccione **confirmar** para guardar los cambios. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Reasignar todos los intervalos órbitas del parque de llamadas con el shell de administración de Skype empresarial Server

1. Abra el shell de administración de Skype empresarial Server.

2. En la línea de comandos, escriba:

   ```
   Get-CsCallParkOrbit
   ```

    Este cmdlet muestra todos los intervalos de la órbita de estacionamiento de llamadas en la implementación. Todas las órbitas de estacionamiento de llamadas que tienen los parámetros **CallParkServiceId** y **CallParkServerFqdn** establecidos como el grupo heredado se deben reasignar. 

    Para reasignar los intervalos de la órbita del parque de llamadas heredadas al grupo de Skype empresarial Server 2019, en la línea de comandos, escriba lo siguiente:

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Después de reasignar todos los intervalos de la gira de llamadas al grupo de servidores de Skype empresarial 2019, se completará el proceso de migración de la aplicación de estacionamiento de llamadas y el grupo de Skype empresarial Server 2019 administrará todas las solicitudes de estacionamiento de llamadas futuras.


