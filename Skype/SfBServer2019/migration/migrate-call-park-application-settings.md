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
description: 'La migración de la aplicación estacionamiento de llamadas incluye aprovisionar el grupo de servidores de Skype Empresarial Server 2019 con cualquier música personalizada en espera que se haya cargado en la instalación heredada, restaurar la configuración del nivel de servicio y volver a dirigir todas las órbitas de estacionamiento de llamadas al grupo de servidores de Skype Empresarial Server 2019. Si se han configurado archivos de música en espera personalizados en el grupo de servidores, estos archivos deben copiarse en el nuevo grupo de servidores Skype Empresarial Server 2019. Además, se recomienda realizar una copia de seguridad de los archivos de música en espera personalizados de Estacionamiento de llamadas desde otro destino para mantener una copia de seguridad independiente de cualquier archivo de música en espera personalizado que se haya cargado para el estacionamiento de llamadas. Los archivos de música en espera personalizados para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo de servidores. Para copiar los archivos de audio de un almacén de archivos de grupo en un almacén de archivos de Skype Empresarial Server 2019, use el comando Xcopy con los siguientes parámetros:'
ms.openlocfilehash: f83e1095361ddd272a35bf9100171c0d06caf003dfae84f19c01b2aa53de7977
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312328"
---
# <a name="migrate-call-park-application-settings"></a>Migrar la configuración de la aplicación de estacionamiento de llamadas

La migración de la aplicación estacionamiento de llamadas incluye aprovisionar el grupo de servidores de Skype Empresarial Server 2019 con cualquier archivo de música en espera personalizado que se haya cargado en la instalación heredada, restaurar la configuración de nivel de servicio y volver a dirigir todas las órbitas de estacionamiento de llamadas al grupo de servidores de Skype Empresarial Server 2019. Si se han configurado archivos de música en espera personalizados en el grupo de servidores, estos archivos deben copiarse en el nuevo grupo de servidores Skype Empresarial Server 2019. Además, se recomienda realizar una copia de seguridad de los archivos de música en espera personalizados de estacionamiento de llamadas en otro destino para mantener una copia de seguridad independiente de cualquier archivo de música en espera personalizado que se haya cargado para el estacionamiento de llamadas. Los archivos de música en espera personalizados para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo de servidores. Para copiar los archivos de audio de un almacén de archivos de grupo en un almacén de archivos de Skype Empresarial Server 2019, use el **comando Xcopy** con los siguientes parámetros: 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Cuando todos los archivos de audio personalizados se han copiado en el almacén de archivos de Skype Empresarial Server 2019, la configuración de la aplicación estacionamiento de llamadas del grupo de servidores de Skype Empresarial Server 2019 debe configurarse y los intervalos de órbitas de estacionamiento de llamadas asociados con el grupo heredado deben reasignarse al grupo de servidores de Skype Empresarial Server 2019.

La configuración de la aplicación estacionamiento de llamadas incluye el umbral de tiempo de espera de recogida, habilitar o deshabilitar la música en espera, los intentos máximos de recogida de llamadas y la solicitud de tiempo de espera. Debe administrar la configuración de la aplicación estacionamiento de llamadas mediante el Shell de administración de Skype Empresarial Server para ejecutar el cmdlet **Set-CsCpsConfiguration.** No puede administrar la configuración de la aplicación estacionamiento de llamadas mediante el Panel Skype Empresarial Server control. 

## <a name="reconfigure-the-call-park-service-settings"></a>Volver a configurar los valores de servicio de estacionamiento de llamadas

1. Desde el Skype Empresarial Server front-end de 2019, abra el Shell Skype Empresarial Server administración.

2. Escriba lo siguiente en la línea de comandos:

    > [!NOTE]
    > Si la Skype Empresarial Server aplicación de estacionamiento de llamadas de 2019 es idéntica a la configuración heredada, puede omitir este paso. Si la configuración de la aplicación estacionamiento de llamadas es diferente para los entornos Skype Empresarial Server 2019 y heredados, use el cmdlet siguiente como plantilla para actualizar esos cambios. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Para reasignar todos los intervalos de órbitas de estacionamiento de llamadas del grupo heredado al grupo de servidores de Skype Empresarial Server 2019, puede usar el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Reasignar todos los rangos de órbitas de estacionamiento de llamadas Skype Empresarial Server panel de control

1. Abra Skype Empresarial Server Panel de control.

2. En el panel izquierdo, seleccione **Características de voz**.

3. Seleccione la pestaña **Estacionamiento de llamadas**. 

4. Para cada intervalo de órbitas de estacionamiento de llamadas asignado a un grupo heredado, edite el **FQDN** del servidor de destino y seleccione el grupo de servidores de Skype Empresarial Server 2019 que procesará las solicitudes de estacionamiento de llamadas. 

5. Seleccione **Confirmar** para guardar los cambios. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Reasignar todos los rangos de órbitas de estacionamiento de llamadas Skype Empresarial Server Shell de administración

1. Abra Skype Empresarial Server Shell de administración.

2. En la línea de comandos, escriba lo siguiente:

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Este cmdlet muestra todos los intervalos de órbita de estacionamiento de llamadas de la implementación. Todas las órbitas de estacionamiento de llamadas que tienen los parámetros **CallParkServiceId** y **CallParkServerFqdn** establecidos como el grupo heredado deben reasignarse. 

    Para reasignar los intervalos de órbitas de estacionamiento de llamadas heredados al grupo de servidores de Skype Empresarial Server 2019, en la línea de comandos, escriba lo siguiente:

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Después de reasignar todos los intervalos de órbitas de estacionamiento de llamadas al grupo de servidores de Skype Empresarial Server 2019, se completará el proceso de migración de la aplicación estacionamiento de llamadas y el grupo de servidores de Skype Empresarial Server 2019 controlará todas las solicitudes futuras de estacionamiento de llamadas.


