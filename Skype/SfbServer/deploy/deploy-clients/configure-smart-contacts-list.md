---
title: Configurar la lista de contactos inteligentes en Skype Empresarial Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Resumen: Conozca cómo activar la característica de lista de contactos inteligente en el Skype para cliente de empresa.'
ms.openlocfilehash: f5b5b8f7baa0ce848765a0f2b62aabb118ecb224
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-smart-contacts-list-in-skype-for-business-server"></a>Configurar la lista de contactos inteligentes en Skype Empresarial Server
 
**Resumen:** Aprenda a activar la característica de lista de contactos inteligente en el Skype para cliente de empresa.
  
La característica Lista de contactos inteligentes permite rellenar automáticamente las listas de contactos de los usuarios finales. Tras la primera utiliza Skype para el negocio, su voluntad de los usuarios automáticamente consulte su administrador y otras personas de su equipo. Esta característica está activada de forma predeterminada para los usuarios de Office 365, pero debe habilitar explícitamente esta característica para los usuarios locales mediante la configuración de la directiva de cliente.
  
Tenga en cuenta lo siguiente al configurar esta característica:
  
- Usuarios, hasta 13, se agregan automáticamente a la lista de contactos inteligente en el orden siguiente:
    
  1. Administrador
    
  2. Directos en orden alfabético
    
  3. Compañeros en orden alfabético
    
- La primera vez que un usuario inicia sesión, se crea un grupo llamado Mi grupo. El grupo se rellena automáticamente con las personas en relación de grupo de AD del usuario basada en el alias de usuario rellenado en el campo Gestor. Tenga en cuenta que los cambios realizados en la pertenencia a un grupo de AD no se actualizan en Mi grupo después de haberse rellenado inicialmente. Si un usuario elimina un contacto o el grupo, ni el contacto ni el grupo se volverán a crear. 
    
- Si el etiquetado automático está activado, los contactos de la lista estarán etiquetados para cambios de presencia. El etiquetado automático está activado de forma predeterminada, pero puede elegir desactivarlo. 
    
- Se informará a todos los nuevos usuarios del grupo que han sido agregados a la lista de contactos. Los usuarios pueden agregar de forma manual nuevos miembros a su instancia de Mi grupo o a otros grupos que elijan.
    
- Esta característica solo funciona con usuarios que inician sesión la primera vez. Si un usuario ha iniciado sesión anteriormente desde cualquier dispositivo (por ejemplo, un dispositivo móvil o un equipo Mac), esta característica no estará habilitada para ese usuario.
    
## <a name="configure-smart-contacts-list"></a>Configurar la lista de contactos inteligentes

Para habilitar la lista de contactos inteligentes para los usuarios, tendrá que completar los pasos siguientes: 
  
- Crear una nueva entrada de CsClientPolicy y agregarlo a la directiva de cliente global. 
    
- Asegúrese de que la opción Búsqueda de la Libreta de direcciones esté configurada solo para búsqueda en la web.
    
### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Crear una entrada de directiva para habilitar la lista de contactos inteligentes

Para crear una entrada de directiva para habilitar la característica de lista de contactos inteligente, utilice el cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) con la opción EnableClientAutoPopulateWithTeam:
  
```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

A continuación, utilice el cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) para escribir los cambios en la directiva global de la siguiente manera:
  
```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

De manera opcional, puede crear una directiva para desactivar el etiquetado automático, como se indica a continuación:
  
```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}

```

Además, tiene que configurar el parámetro AddressBookAvailability para la directiva correspondiente en WebSearchOnly. Para obtener más información, consulte [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 
  
### <a name="troubleshoot"></a>Solución de problemas

Si la lista de contactos inteligentes no funciona según lo esperado, compruebe lo siguiente:
  
- Valide la configuración. 
    
- Confirme que la información de organización de AD se llena.
    
- Recopilar Skype para los registros de cliente de empresa en un nuevo usuario para su posterior análisis.
    
- Confirme que el Skype para la IU de cliente de empresa no muestra un mensaje que no puede conectarse a la libreta de direcciones. Para confirmar la conectividad de la libreta de direcciones, realizar una búsqueda de un usuario en el Skype de barra de búsqueda de cliente de empresa.
    
- Si hay problemas para conectar con la libreta de direcciones, use STrace para recopilar seguimientos de HTTPS y HTTPReplay para analizar los seguimientos recopilados. Para obtener más información, consulte el [blog relacionado registrar](https://blogs.msdn.microsoft.com/canberrapfe/2012/06/04/have-you-ever-wondered-what-web-service-urls-are-used-by-the-lync-client-strace-is-your-tool/).
    
- Problemas de replicación de AD DS podrían provocar contactos sin resolver cuando un usuario primero inicia sesión Skype para el negocio.
    

