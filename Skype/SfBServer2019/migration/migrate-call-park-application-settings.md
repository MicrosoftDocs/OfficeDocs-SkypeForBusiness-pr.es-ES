---
title: Migrar la configuración de la aplicación de estacionamiento de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'La migración de la aplicación incluye la Skype para grupo de negocio Server 2019 con cualquier personalizado de música en espera los archivos que se han cargado en la instalación heredada de aprovisionamiento de estacionamiento de llamadas, al restaurar la configuración de nivel de servicio y redirección de estacionamiento todas las órbitas a la Skype para el grupo de servidores de Business Server 2019. Si se han configurado en el grupo de archivos de música en espera personalizados, estos archivos deben copiarse a la nueva Skype para el grupo de servidores de Business Server 2019. Además, se recomienda que se haga una copia de seguridad de cualquier estacionamiento personalizado los archivos de música en espera de a otro destino para mantener una copia de seguridad independiente de cualquier archivo personalizado de música en espera que se han cargado del estacionamiento de llamadas. Los archivos de música en espera personalizados para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo de servidores. Para copiar los archivos de audio desde un almacén de archivos de grupo de servidores a un Skype Business Server 2019 almacén de archivos, utilice el comando Xcopy con los siguientes parámetros:'
ms.openlocfilehash: 3d9c2904d66ac5d35bdd94631ec23c67288a5c3a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887626"
---
# <a name="migrate-call-park-application-settings"></a>Migrar la configuración de la aplicación de estacionamiento de llamadas

La migración de la aplicación de estacionamiento de llamadas incluye la Skype para el grupo de servidores de Business Server 2019 de aprovisionamiento con cualquier archivo de música en espera personalizado que se han cargado en la instalación heredada, al restaurar la configuración de nivel de servicio e identificación de volver a todas las órbitas de estacionamiento de llamadas para Skype para el grupo de servidores de Business Server 2019. Si se han configurado en el grupo de archivos de música en espera personalizados, estos archivos deben copiarse a la nueva Skype para el grupo de servidores de Business Server 2019. Además, se recomienda que se haga una copia de seguridad de cualquier estacionamiento personalizado los archivos de música en espera a otro destino para mantener una copia de seguridad independiente de cualquier archivo personalizado de música en espera que se han cargado del estacionamiento de llamadas. Los archivos de música en espera personalizados para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo de servidores. Para copiar los archivos de audio desde un almacén de archivos de grupo de servidores a un Skype Business Server 2019 almacén de archivos, utilice el comando **Xcopy** con los siguientes parámetros: 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Cuando se han copiado todos los archivos de audioconferencias personalizados a la Skype Business Server 2019 almacén de archivos, la configuración de la aplicación de estacionamiento de llamadas de la Skype para Business Server 2019 se debe configurar el grupo de servidores y el estacionamiento de llamadas órbita rangos que están asociados con el grupo de servidores heredado debe asignarse a la Skype para el grupo de servidores de Business Server 2019.

La configuración de la aplicación de estacionamiento de llamadas incluye el umbral de tiempo de espera pickup, habilitar o deshabilitar la música en espera, los intentos de recogida máximo de llamadas y la solicitud de tiempo de espera. Debe administrar configuración de la aplicación de estacionamiento de llamadas mediante el Skype para Business Server Management Shell para ejecutar el cmdlet **Set-CsCpsConfiguration** . No se puede administrar la configuración de la aplicación de estacionamiento de llamadas mediante el Skype para el Panel de Control de servidor empresarial. 

## <a name="reconfigure-the-call-park-service-settings"></a>Volver a configurar la configuración del servicio de estacionamiento de llamadas

1. De Skype para profesionales de 2019 Front-End Server, abra el Skype para Shell de administración de servidor empresarial.

2. En la línea de comandos, escriba:

    > [!NOTE]
    > Si su Skype para la configuración de la aplicación de estacionamiento de llamadas de Business Server 2019 es idéntica a la configuración heredada, puede omitir este paso. Si la configuración de la aplicación de estacionamiento de llamadas es diferentes para la Skype para Business Server 2019 y entornos heredados, use el cmdlet a continuación como una plantilla para actualizar dichos cambios. 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Para reasignar todos los intervalos de órbitas de estacionamiento de llamadas del grupo heredado para la Skype para Business Server 2019 grupo, puede usar el Skype para el Panel de Control de servidor empresarial o el Skype para Shell de administración de servidor empresarial. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Reasignar todos los intervalos de órbitas de estacionamiento de llamadas mediante Skype para el Panel de Control de servidor empresarial

1. Abra Skype para el Panel de Control de servidor empresarial.

2. En el panel izquierdo, seleccione **Las características de voz**.

3. Seleccione la pestaña **Estacionamiento de llamadas** . 

4. Para cada intervalo de órbitas de estacionamiento de llamadas asignado a un grupo de servidores heredado, edite la configuración del **FQDN del servidor de destino** y seleccione el Skype para grupo de negocio Server 2019 que procesará las solicitudes de estacionamiento de llamadas. 

5. Seleccione **Confirmar** para guardar los cambios. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Reasignar todos los intervalos de órbitas de estacionamiento de llamadas mediante Skype para Shell de administración de servidor empresarial

1. Abra Skype para Shell de administración de servidor empresarial.

2. En la línea de comandos, escriba:

   ```
   Get-CsCallParkOrbit
   ```

    Este cmdlet enumera todos los intervalos de órbitas de estacionamiento de llamadas en la implementación. Se deben reasignar todas las órbitas de estacionamiento de llamadas que tienen los parámetros **CallParkServiceId** y **CallParkServerFqdn** establecido como el grupo heredado. 

    Para volver a asignar la órbita de estacionamiento de llamadas heredada intervalos a la Skype para Business Server 2019 grupo de servidores, en la línea de comandos, escriba lo siguiente:

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Después de reasignar todos los intervalos de órbitas de estacionamiento de llamadas a la Skype para el grupo de servidores de Business Server 2019, se completará el proceso de migración de la aplicación de estacionamiento de llamadas y el Skype para el grupo de servidores de Business Server 2019 controlará todas las solicitudes futuras de estacionamiento de llamadas.


