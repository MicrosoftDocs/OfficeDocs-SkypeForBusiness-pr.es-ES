---
title: Configuración de lista de contactos inteligente en Skype para clientes empresariales
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Resumen: Obtenga información sobre cómo activar la característica de lista de contactos inteligente en el Skype para clientes empresariales.'
ms.openlocfilehash: 72e8a2e5eb0640215ac4512ff210d30f31295fd8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20976215"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Configuración de lista de contactos inteligente en Skype para clientes empresariales
 
**Resumen:** Obtenga información sobre cómo activar la característica de lista de contactos inteligente en el Skype para clientes empresariales.
  
La característica Lista de contactos inteligentes permite rellenar automáticamente las listas de contactos de los usuarios finales. Tras la primera usar Skype para la empresa, su voluntad de los usuarios automáticamente vea su director y otras personas de su equipo. Esta característica está activada de forma predeterminada para los usuarios de Office 365, pero debe habilitar esta característica explícitamente para los usuarios locales mediante la configuración de la configuración de directiva de cliente.
  
Tenga en cuenta lo siguiente al configurar esta característica:
  
- Los usuarios, hasta 13, se agregan automáticamente a la lista de contactos inteligente en el orden siguiente:
    
  1. Administrador
    
  2. Directos en orden alfabético
    
  3. Compañeros en orden alfabético
    
- La primera vez que un usuario inicia sesión, se crea un grupo llamado Mi grupo. El grupo se rellena automáticamente con las personas de la relación de grupo de AD del usuario basada en el alias de usuario rellenado en el campo de administrador. Tenga en cuenta que los cambios realizados en la pertenencia a un grupo de AD no se actualizan en Mi grupo después de haberse rellenado inicialmente. Si un usuario elimina un contacto o el grupo, ni el contacto ni el grupo se volverán a crear. 
    
- Si el etiquetado automático está activado, los contactos de la lista estarán etiquetados para cambios de presencia. El etiquetado automático está activado de forma predeterminada, pero puede elegir desactivarlo. 
    
- Se informará a todos los nuevos usuarios del grupo que han sido agregados a la lista de contactos. Los usuarios pueden agregar de forma manual nuevos miembros a su instancia de Mi grupo o a otros grupos que elijan.
    
- Esta característica solo funciona con usuarios que inician sesión la primera vez. Si un usuario ha iniciado sesión anteriormente desde cualquier dispositivo (por ejemplo, un dispositivo móvil o un equipo Mac), esta característica no estará habilitada para ese usuario.
    
## <a name="configure-smart-contacts-list"></a>Configurar la lista de contactos inteligentes

Para habilitar la lista de contactos inteligentes para los usuarios, tendrá que completar los pasos siguientes: 
  
- Crear una nueva entrada de CsClientPolicy y agregarlo a la directiva global de cliente. 
    
- Asegúrese de que la opción Búsqueda de la Libreta de direcciones esté configurada solo para búsqueda en la web.
    
### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Crear una entrada de directiva para habilitar la lista de contactos inteligentes

Para crear una entrada de directiva para habilitar la característica de lista de contactos inteligente, utilice el cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) con la opción EnableClientAutoPopulateWithTeam como se indica a continuación:
  
```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

A continuación, use el cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) para escribir los cambios en la directiva global de la siguiente manera:
  
```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

De manera opcional, puede crear una directiva para desactivar el etiquetado automático, como se indica a continuación:
  
```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}

```

Además, tiene que configurar el parámetro AddressBookAvailability para la directiva correspondiente en WebSearchOnly. Para obtener más información, vea [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 
  
### <a name="troubleshoot"></a>Solución de problemas

Si la lista de contactos inteligentes no funciona según lo esperado, compruebe lo siguiente:
  
- Valide la configuración. 
    
- Confirme que la información de la organización de AD está rellenada.
    
- Recopilar Skype para los registros del cliente empresarial en un nuevo usuario para realizar un análisis.
    
- Confirme que la Skype para la interfaz de usuario de cliente de negocio no muestra un mensaje que no puede conectarse a la libreta de direcciones. Para confirmar la conectividad de la libreta de direcciones, realice una búsqueda de un usuario en el Skype para la barra de búsqueda de cliente de empresa.
    
- Problemas de replicación de AD DS podrían provocar que los contactos a sin resolver cuando un usuario primero inicia sesión en Skype para la empresa.
    

