---
title: Migrar la configuración de la aplicación de estacionamiento de llamadas
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'La migración de la aplicación de estacionamiento de llamadas incluye el aprovisionamiento del grupo de Skype empresarial Server 2019 con cualquier archivo de música personalizado en retención que se haya cargado en la instalación heredada, restaurando la configuración del nivel de servicio y redestinando todas las órbitas de estacionamiento de llamadas al grupo de servidores de Skype empresarial 2019. Si se han configurado archivos de música en espera personalizados en el grupo, estos archivos deben copiarse en el nuevo grupo de servidores de Skype empresarial 2019. Además, se recomienda realizar una copia de seguridad de los archivos de música en espera personalizados de la música en espera de cualquier otro destino para mantener una copia de seguridad independiente de los archivos de música en espera personalizados que se hayan cargado para el estacionamiento de llamadas. Los archivos de música en espera personalizados para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo de servidores. Para copiar los archivos de audio de un almacén de archivos de grupo a un almacén de archivos de Skype empresarial Server 2019, use el comando xcopy con los parámetros siguientes:'
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752822"
---
# <a name="migrate-call-park-application-settings"></a>Migrar la configuración de la aplicación de estacionamiento de llamadas

La migración de la aplicación de estacionamiento de llamadas incluye el aprovisionamiento del grupo de Skype empresarial Server 2019 con cualquier archivo de música en espera personalizado que se haya cargado en la instalación heredada, restaurar la configuración de nivel de servicio y volver a dirigir todas las órbitas de estacionamiento de llamadas al grupo de Skype empresarial Server 2019. Si se han configurado archivos de música en espera personalizados en el grupo, estos archivos deben copiarse en el nuevo grupo de servidores de Skype empresarial 2019. Además, se recomienda que realice una copia de seguridad de los archivos de música en espera personalizados de la música en espera en otro destino para mantener una copia de seguridad independiente de los archivos de música en espera personalizados que se hayan cargado para el estacionamiento de llamadas. Los archivos de música en espera personalizados para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo de servidores. Para copiar los archivos de audio de un almacén de archivos de grupo a un almacén de archivos de Skype empresarial Server 2019, use el comando **xcopy** con los parámetros siguientes: 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Cuando todos los archivos de audio personalizados se han copiado en el almacén de archivos de Skype empresarial Server 2019, la configuración de la aplicación de estacionamiento de llamadas del grupo de Skype empresarial Server 2019 debe estar configurada, y los intervalos de órbita de estacionamiento de llamadas asociados con el grupo de servidores heredados deben reasignarse al grupo de Skype empresarial Server 2019.

La configuración de la aplicación estacionamiento de llamadas incluye el umbral de tiempo de espera de recogida, la habilitación o deshabilitación de la música en espera, los intentos máximos de recogida de llamadas y la solicitud de tiempo de espera. Debe administrar la configuración de la aplicación de estacionamiento de llamadas mediante el shell de administración de Skype empresarial Server para ejecutar el cmdlet **set-CsCpsConfiguration** . No puede administrar la configuración de la aplicación estacionamiento de llamadas mediante el panel de control de Skype empresarial Server. 

## <a name="reconfigure-the-call-park-service-settings"></a>Volver a configurar los valores de servicio de estacionamiento de llamadas

1. En el servidor front-end de Skype empresarial Server 2019, abra el shell de administración de Skype empresarial Server.

2. Escriba lo siguiente en la línea de comandos:

    > [!NOTE]
    > Si su configuración de la aplicación de estacionamiento de llamadas de Skype empresarial Server 2019 es idéntica a la configuración heredada, puede omitir este paso. Si la configuración de la aplicación estacionamiento de llamadas es diferente para los entornos heredados y de Skype empresarial Server 2019, use el cmdlet siguiente como plantilla para actualizar dichos cambios. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Para reasignar todos los intervalos de órbitas de estacionamiento de llamadas desde el grupo heredado al grupo de Skype empresarial Server 2019, puede usar el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial Server. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Reasignar todos los intervalos de órbitas de estacionamiento de llamadas mediante el panel de control de Skype empresarial Server

1. Abra el panel de control de Skype empresarial Server.

2. En el panel izquierdo, seleccione **Características de voz**.

3. Seleccione la pestaña **Estacionamiento de llamadas**. 

4. Para cada intervalo de órbitas de estacionamiento de llamadas asignado a un grupo de servidores heredado, edite el **FQDN del servidor de destino** y seleccione el grupo de servidores de Skype empresarial 2019 que procesará las solicitudes de estacionamiento de llamadas. 

5. Seleccione **Confirmar** para guardar los cambios. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Reasignar todos los intervalos de órbitas de estacionamiento de llamadas con el shell de administración de Skype empresarial Server

1. Abra el shell de administración de Skype empresarial Server.

2. En la línea de comandos, escriba lo siguiente:

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Este cmdlet muestra todos los intervalos de órbita de estacionamiento de llamadas de la implementación. Todas las órbitas de estacionamiento de llamadas que tienen los parámetros **CallParkServiceId** y **CallParkServerFqdn** establecidos como grupo heredado deben reasignarse. 

    Para reasignar intervalos de órbita de estacionamiento de llamadas heredadas al grupo de Skype empresarial Server 2019, escriba lo siguiente en la línea de comandos:

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Después de reasignar todos los intervalos de órbita de estacionamiento de llamadas al grupo de servidores de Skype empresarial Server 2019, se completará el proceso de migración de la aplicación de estacionamiento de llamadas y el grupo de servidores de Skype empresarial 2019 administrará todas las solicitudes de estacionamiento de llamadas futuras.


