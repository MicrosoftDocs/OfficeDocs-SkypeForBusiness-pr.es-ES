---
title: Configurar la lista Smart Contacts en clientes de Skype empresarial
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
description: 'Resumen: Obtenga información sobre cómo activar la característica lista de contactos inteligente en el cliente de Skype empresarial.'
ms.openlocfilehash: 9db4e6616aa4c11be3ad2f9ee1cd92a0587b4e51
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768873"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Configurar la lista Smart Contacts en clientes de Skype empresarial

**Resumen:** Obtenga información sobre cómo activar la característica lista de contactos inteligente en el cliente de Skype empresarial.

La característica Lista de contactos inteligentes permite rellenar automáticamente las listas de contactos de los usuarios finales. La primera vez que use Skype empresarial, los usuarios verán automáticamente a su jefe y a otras personas de su equipo. Esta característica está activada de forma predeterminada para los usuarios de Office 365, pero debe habilitarla de forma explícita para los usuarios locales mediante la configuración de la Directiva de cliente.

Tenga en cuenta lo siguiente al configurar esta característica:

- Los usuarios, hasta 13, se agregan automáticamente a la lista de contactos inteligente en el siguiente orden:

  1. Administrador

  2. Directos en orden alfabético

  3. Compañeros en orden alfabético

- La primera vez que un usuario inicia sesión, se crea un grupo llamado Mi grupo. El grupo se rellena automáticamente con las personas de la relación de grupo de AD del usuario en función del alias de usuario rellenado en el campo administrador. Tenga en cuenta que los cambios realizados en la pertenencia a un grupo de AD no se actualizan en Mi grupo después de haberse rellenado inicialmente. Si un usuario elimina un contacto o el grupo, ni el contacto ni el grupo se volverán a crear. 

- Si el etiquetado automático está activado, los contactos de la lista estarán etiquetados para cambios de presencia. El etiquetado automático está activado de forma predeterminada, pero puede elegir desactivarlo. 

- Se informará a todos los nuevos usuarios del grupo que han sido agregados a la lista de contactos. Los usuarios pueden agregar de forma manual nuevos miembros a su instancia de Mi grupo o a otros grupos que elijan.

- Esta característica solo funciona con usuarios que inician sesión la primera vez. Si un usuario ha iniciado sesión anteriormente desde cualquier dispositivo (por ejemplo, un dispositivo móvil o un equipo Mac), esta característica no estará habilitada para ese usuario.

## <a name="configure-smart-contacts-list"></a>Configurar la lista de contactos inteligentes

Para habilitar la lista de contactos inteligentes para los usuarios, tendrá que completar los pasos siguientes: 

- Cree una nueva entrada de ClientPolicy y agréguela a la Directiva de cliente global. 

- Asegúrese de que la opción Búsqueda de la Libreta de direcciones esté configurada solo para búsqueda en la web.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Crear una entrada de directiva para habilitar la lista de contactos inteligentes

Para crear una entrada de directiva para habilitar la característica de lista de contactos inteligente, use el cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) con la opción EnableClientAutoPopulateWithTeam de la siguiente manera:

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

A continuación, use el cmdlet [set-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) para escribir los cambios en la directiva global de la siguiente manera:

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

De manera opcional, puede crear una directiva para desactivar el etiquetado automático, como se indica a continuación:

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Además, tiene que configurar el parámetro AddressBookAvailability para la directiva correspondiente en WebSearchOnly. Para obtener más información, consulte [set-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Solución de problemas

Si la lista de contactos inteligentes no funciona según lo esperado, compruebe lo siguiente:

- Valide la configuración. 

- Confirme que la información de la organización de AD está rellenada.

- Recopilar registros de clientes de Skype empresarial en un nuevo usuario para analizarlos más.

- Confirme que la interfaz de usuario del cliente de Skype empresarial no muestra un mensaje que indica que no se puede conectar con la libreta de direcciones. Para confirmar la conectividad de la libreta de direcciones, busque un usuario en la barra de búsqueda del cliente de Skype empresarial.

- Los problemas de replicación de AD DS pueden provocar que los contactos no se resuelvan cuando un usuario inicia sesión en Skype empresarial por primera vez.


