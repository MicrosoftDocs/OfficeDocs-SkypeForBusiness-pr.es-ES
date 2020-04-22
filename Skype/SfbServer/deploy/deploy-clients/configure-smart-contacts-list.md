---
title: Configurar la lista de contactos inteligentes en clientes de Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Resumen: Obtenga información sobre cómo activar la característica lista de contactos inteligentes en el cliente de Skype empresarial.'
ms.openlocfilehash: d99008cde28b834f77a2935ffd7882162aa05e95
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776695"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Configurar la lista de contactos inteligentes en clientes de Skype empresarial

**Resumen:** Obtenga información sobre cómo activar la característica lista de contactos inteligentes en el cliente de Skype empresarial.

La característica lista de contactos inteligentes permite rellenar automáticamente las listas de contactos para los usuarios finales. La primera vez que use Skype empresarial, los usuarios verán automáticamente a su administrador y a otras personas de su equipo. Esta característica está activada de forma predeterminada para los usuarios de Microsoft 365 y Office 365, pero debe habilitarse de forma explícita esta característica para los usuarios locales mediante la configuración de la Directiva de cliente.

Tenga en cuenta lo siguiente al configurar esta característica:

- Los usuarios, hasta 13, se agregan automáticamente a la lista de contactos inteligentes en el siguiente orden:

  1. Manager

  2. Se dirige en orden alfabético

  3. Elementos del mismo nivel en orden alfabético

- La primera vez que un usuario inicia sesión, se crea un nuevo grupo denominado mi grupo. El grupo se rellena automáticamente con personas en la relación de grupo de AD del usuario en función del alias de usuario rellenado en el campo administrador. Tenga en cuenta que los cambios en la pertenencia al grupo de AD no causan actualizaciones a mi grupo una vez que se ha rellenado inicialmente. Si un usuario elimina un contacto o el grupo, no se volverán a crear ni el contacto ni el grupo. 

- Si el etiquetado automático está activado, los contactos de la lista se etiquetarán para cambios de presencia. El etiquetado automático está activado de forma predeterminada, pero puede elegir desactivarlo. 

- Se informará a todos los usuarios nuevos del grupo que se han agregado a la lista de contactos. Los usuarios pueden agregar manualmente nuevos miembros a su grupo o a otros grupos de su elección.

- Esta característica solo funciona para los usuarios que inician sesión por primera vez. Si un usuario ha iniciado sesión previamente desde cualquier dispositivo, incluido, por ejemplo, un dispositivo móvil o un Mac, la característica no está habilitada para ese usuario.

## <a name="configure-smart-contacts-list"></a>Configurar la lista de contactos inteligentes

Para habilitar la característica lista de contactos inteligentes para los usuarios, deberá realizar los siguientes pasos: 

- Cree una nueva entrada de CsClientPolicy y agréguela a la Directiva de cliente global. 

- Asegúrese de que la búsqueda de la libreta de direcciones esté configurada solo para búsqueda web.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Crear una entrada de directiva para habilitar la lista de contactos inteligentes

Para crear una entrada de directiva para habilitar la característica lista de contactos inteligentes, use el cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) con la opción enableclientautopopulatewithteam, de la siguiente manera:

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

A continuación, use el cmdlet [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) para escribir los cambios en la directiva global de la siguiente manera:

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Opcionalmente, puede crear una directiva para desactivar el etiquetado automático de la siguiente manera:

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

También debe establecer el parámetro AddressBookAvailability de la directiva correspondiente en WebSearchOnly. Para obtener más información, vea [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Solucionar problemas

Si la lista de contactos inteligentes no funciona como se esperaba, compruebe lo siguiente:

- Validar la configuración. 

- Confirme que la información de la organización de AD está rellenada.

- Recopilar registros de clientes de Skype empresarial en un nuevo usuario para un análisis más detallada.

- Confirme que la interfaz de usuario del cliente de Skype empresarial no muestra un mensaje que indica que no se puede conectar a la libreta de direcciones. Para confirmar la conectividad de la libreta de direcciones, realice una búsqueda para un usuario en la barra de búsqueda del cliente de Skype empresarial.

- Los problemas de replicación de AD DS podrían hacer que los contactos no se resuelvan cuando un usuario inicia sesión por primera vez en Skype empresarial.


