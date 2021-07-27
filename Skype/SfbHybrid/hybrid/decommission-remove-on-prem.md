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
ms.openlocfilehash: bdd38578d8ee98c26e6515c1cd4baa0ef8a825cf
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510791"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>Eliminar la implementación local de Skype Empresarial

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

En este artículo se describe cómo quitar la implementación Skype Empresarial local. Este es el paso 4 de los siguientes pasos para retirar el entorno local:

- Paso 1. [Mueva todos los usuarios necesarios de local a en línea.](decommission-move-on-prem-users.md) 

- Paso 2. [Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).

- Paso 3. [Migrar puntos de conexión de aplicaciones híbridas de local a online](decommission-move-on-prem-endpoints.md)

- **Paso 4. Quite la implementación Skype Empresarial local.** (Este artículo)


> [!IMPORTANT] 
> Los pasos de este artículo solo se aplican si usa el método 2 para administrar atributos de usuario, como se describe [aquí](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory). Si usa el método 1, no use los pasos descritos en este artículo para quitar los Skype Empresarial servidores. En su lugar, puede volver a crear una imagen de los servidores.

Para completar los pasos de este artículo, necesita privilegios tanto para el grupo Administradores de esquema como para el grupo Enterprise administración. Necesitará estos privilegios para deshacer el esquema Skype Empresarial Server y los cambios de nivel de bosque en los Servicios de dominio de Active Directory. También tendrá que ser miembro del grupo RTCUniversalServerAdmins.


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>Prepararse para quitar la Skype Empresarial implementación

Después de mover todas las cuentas de usuario necesarias a la nube, es posible que aún haya algunos objetos locales restantes, como contactos y aplicaciones, que necesitará limpiar.

Siga los pasos siguientes para limpiar estos objetos y asegúrese de que es miembro del grupo Administrador local y del grupo RTCUniversalServerAdmins. Tenga en cuenta que ExUmContacts y PersistantChatEndPoints no están disponibles en Skype Empresarial Server 2019. Si ha Skype Empresarial Server 2019, se deben omitir los cmdlets correspondientes en los pasos siguientes.

1. Para comprobar si hay contactos o aplicaciones asociados con la implementación Skype Empresarial Server local, ejecute los siguientes cmdlets Skype Empresarial Server PowerShell.

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
2. Revise las listas de resultados de los cmdlets del paso 1. A continuación, si se pueden quitar objetos, ejecute los siguientes cmdlets Skype Empresarial Server PowerShell:

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

Después de completar todos los pasos preliminares, puede quitar la Skype Empresarial implementación siguiendo estos pasos:

1. Quite lógicamente la implementación Skype Empresarial Server, excepto para un único front-end, como se muestra a continuación:

   1. Actualice su Skype Empresarial Server topología para que tenga un único grupo de servidores front-end:

      1. En el Generador de topologías, descargue una nueva copia y vaya al grupo de servidores front-end.
      1. Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.
      1. En **Asociaciones**, desactive **Asociar grupo perimetral** (para componentes multimedia) y haga clic en **Aceptar**.
      1. Si hay más de un grupo de servidores front-end, quite las asociaciones de todos los grupos restantes.
      1. Seleccione **Acción > Quitar implementación**.
      1. Seleccione **Acción > Publicar topología**.

    1. Después de publicar la topología, complete los pasos adicionales descritos en el asistente.

2. Quite Skype Empresarial Server directorios de conferencia ejecutando el siguiente cmdlet Skype Empresarial Server PowerShell:

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. Para finalizar la desinstalación de la Skype Empresarial Server implementación, ejecute el siguiente cmdlet Skype Empresarial Server PowerShell:

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > Si este paso devuelve un error, abra un vale de soporte técnico de Microsoft para obtener ayuda para quitar los objetos obsoletos restantes.

4. Quite el punto de control del servicio del almacén de administración central ejecutando el siguiente cmdlet Skype Empresarial Server PowerShell:

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. Para deshacer Skype Empresarial Server de dominio de Active Directory, ejecute el siguiente cmdlet Skype Empresarial Server PowerShell:

   ```PowerShell
   Disable-CsAdDomain
   ```
6. Deshaz Skype Empresarial Server cambios en el nivel de bosque de Active Directory ejecutando el siguiente cmdlet Skype Empresarial Server PowerShell:

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>Vea también

- [Retirar el entorno local de Skype Empresarial](decommission-on-prem-overview.md)

- [Mover todos los usuarios necesarios de local a online](decommission-move-on-prem-users.md)

- [Deshabilitar la configuración híbrida](cloud-consolidation-disabling-hybrid.md)

- [Mover puntos de conexión de aplicaciones híbridas de local a online](decommission-move-on-prem-endpoints.md)

