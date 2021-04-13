---
title: Retirar Skype Empresarial Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instrucciones para retirar Skype Empresarial Server.
ms.openlocfilehash: 9c6051a07fc05297985b3692351c36791d8842bb
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656696"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>Eliminar la implementación local de Skype Empresarial

En este artículo se describe cómo quitar la implementación local de Skype Empresarial. Este es el paso 4 de los siguientes pasos para retirar el entorno local:

- Paso 1. [Mueva todos los usuarios necesarios de local a en línea.](decommission-move-on-prem-users.md) 

- Paso 2. [Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).

- Paso 3. [Mover puntos de conexión de aplicaciones híbridas de local a online](decommission-move-on-prem-endpoints.md)

- **Paso 4. Quite la implementación local de Skype Empresarial.** (Este artículo)


> [!IMPORTANT] 
> Los pasos de este artículo solo se aplican si usa el método 2 para administrar atributos de usuario, como se describe [aquí](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory). Si usa el método 1, no use los pasos descritos en este artículo para quitar los servidores de Skype Empresarial. En su lugar, puede volver a crear una imagen de los servidores.

Para completar los pasos de este artículo, necesita privilegios tanto para el grupo Administradores de esquema como para el grupo Administración de empresa. Necesitará estos privilegios para deshacer el esquema de Skype Empresarial Server y los cambios de nivel de bosque en los Servicios de dominio de Active Directory. También tendrá que ser miembro del grupo RTCUniversalServerAdmins.


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>Prepararse para quitar la implementación de Skype Empresarial

Después de mover todas las cuentas de usuario necesarias a la nube, es posible que aún haya algunos objetos locales restantes, como contactos y aplicaciones, que necesitará limpiar.

Siga los pasos siguientes para limpiar estos objetos y asegúrese de que es miembro del grupo Administrador local y del grupo RTCUniversalServerAdmins. Tenga en cuenta que ExUmContacts y PersistantChatEndPoints no están disponibles en Skype Empresarial Server 2019. Si tiene Skype Empresarial Server 2019, se deben omitir los cmdlets correspondientes en los pasos siguientes.

1. Para comprobar si hay contactos o aplicaciones asociados con la implementación local de Skype Empresarial Server, ejecute los siguientes cmdlets de PowerShell de Skype Empresarial Server.

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. Revise las listas de resultados de los cmdlets del paso 1. A continuación, si se pueden quitar objetos, ejecute los siguientes cmdlets de PowerShell de Skype Empresarial Server:

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a>Eliminar la implementación local de Skype Empresarial

Después de completar todos los pasos preliminares, puede quitar la implementación de Skype Empresarial siguiendo estos pasos:

1. Quite lógicamente la implementación de Skype Empresarial Server, excepto para un único front-end, como se muestra a continuación:

   a. Actualice la topología de Skype Empresarial Server para que tenga un único grupo de servidores front-end:

     - En el Generador de topologías, descargue una nueva copia y vaya al grupo de servidores front-end.
     - Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.
     - En **Asociaciones**, desactive **Asociar grupo perimetral** (para componentes multimedia) y haga clic en **Aceptar**.
     - Si hay más de un grupo de servidores front-end, quite las asociaciones de todos los grupos restantes.
     - Seleccione **Acción > Quitar implementación**.
     - Seleccione **Acción > Publicar topología**.

    b. Después de publicar la topología, complete los pasos adicionales descritos en el asistente.

2. Quite los directorios de conferencia de Skype Empresarial Server ejecutando el siguiente cmdlet de PowerShell de Skype Empresarial Server:

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. Para finalizar la desinstalación de la implementación de Skype Empresarial Server, ejecute el siguiente cmdlet de PowerShell de Skype Empresarial Server:

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > Si este paso devuelve un error, abra un vale de soporte técnico de Microsoft para obtener ayuda para quitar los objetos obsoletos restantes.

4. Para quitar el punto de control de servicio del Almacén de administración central, ejecute el siguiente cmdlet de PowerShell de Skype Empresarial Server:

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. Deshacer los cambios en el nivel de bosque de dominio de Skype Empresarial Server Active Directory ejecutando el siguiente cmdlet de PowerShell de Skype Empresarial Server:

   ```PowerShell
   Disable-CsAdDomain
   ```
6. Deshacer los cambios de esquema de dominio de Skype Empresarial Server Active Directory ejecutando el siguiente cmdlet de PowerShell de Skype Empresarial Server:

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>Recursos adicionales

- [Retirar el entorno local de Skype Empresarial](decommission-on-prem-overview.md)

- [Mover todos los usuarios necesarios de local a online](decommission-move-on-prem-users.md)

- [Deshabilitar la configuración híbrida](cloud-consolidation-disabling-hybrid.md)

- [Mover puntos de conexión de aplicaciones híbridas de local a online](decommission-move-on-prem-endpoints.md)











