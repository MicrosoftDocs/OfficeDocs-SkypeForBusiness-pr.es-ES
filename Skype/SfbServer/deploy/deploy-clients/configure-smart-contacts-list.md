---
title: Configurar la lista de contactos inteligentes en clientes de Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Resumen: obtenga información sobre cómo activar la característica lista de contactos inteligentes en el cliente de Skype Empresarial.'
ms.openlocfilehash: 1f049493d591cd561b87611f8a34f9176ace165a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095804"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Configurar la lista de contactos inteligentes en clientes de Skype Empresarial

**Resumen:** Obtenga información sobre cómo activar la característica lista de contactos inteligentes en el cliente de Skype Empresarial.

La característica lista de contactos inteligentes permite la población automática de listas de contactos para los usuarios finales. Al usar Primero Skype Empresarial, los usuarios verán automáticamente a su administrador y a otras personas de su equipo. Esta característica está activada de forma predeterminada para los usuarios de Microsoft 365 y Office 365, pero debe habilitar explícitamente esta característica para los usuarios locales mediante la configuración de la directiva de cliente.

Tenga en cuenta lo siguiente al configurar esta característica:

- Los usuarios, hasta 13, se agregan automáticamente a la lista de contactos inteligentes en el siguiente orden:

  1. Manager

  2. Dirige en orden alfabético

  3. Pares en orden alfabético

- La primera vez que un usuario inicia sesión, se crea un nuevo grupo, denominado Mi grupo. El grupo se rellena automáticamente con personas en la relación de grupo de AD del usuario en función del alias de usuario rellenado en el campo Administrador. Tenga en cuenta que los cambios en la pertenencia a grupos de AD no provocan actualizaciones en Mi grupo después de rellenarla inicialmente. Si un usuario elimina un contacto o el grupo, no se vuelve a crear el contacto ni el grupo. 

- Si el etiquetado automático está activado, los contactos de la lista se etiquetarán para los cambios de presencia. El etiquetado automático está activado de forma predeterminada, pero puedes desactivarlo. 

- Se informará a todos los nuevos usuarios del grupo de que se han agregado a la lista de contactos. Los usuarios pueden agregar manualmente nuevos miembros a su Mi grupo o a otros grupos de su elección.

- Esta característica solo funciona para los usuarios que inician sesión por primera vez. Si un usuario ha iniciado sesión previamente desde cualquier dispositivo (incluido, por ejemplo, cualquier dispositivo móvil o un Mac), la característica no está habilitada para ese usuario.

## <a name="configure-smart-contacts-list"></a>Configurar la lista de contactos inteligentes

Para habilitar la característica lista de contactos inteligentes para los usuarios, deberá realizar los siguientes pasos: 

- Cree una nueva entrada CsClientPolicy y agrégrela a la directiva de cliente global. 

- Asegúrese de que la búsqueda de libreta de direcciones está configurada solo para la búsqueda web.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Crear una entrada de directiva para habilitar la lista de contactos inteligentes

Para crear una entrada de directiva para habilitar la característica lista de contactos inteligentes, use el cmdlet [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) con la opción EnableClientAutoPopulateWithTeam de la siguiente manera:

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

A continuación, use el cmdlet [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) para escribir los cambios en la directiva global de la siguiente manera:

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Opcionalmente, puede crear una directiva para desactivar el etiquetado automático de la siguiente manera:

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

También debe establecer el parámetro AddressBookAvailability para la directiva correspondiente en WebSearchOnly. Para obtener más información, [vea Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Solucionar problemas

Si la lista de contactos inteligentes no funciona como se esperaba, compruebe lo siguiente:

- Validar la configuración. 

- Confirme que la información de la organización de AD está rellenada.

- Recopilar los registros de cliente de Skype Empresarial en un nuevo usuario para su análisis posterior.

- Confirme que la interfaz de usuario del cliente de Skype Empresarial no muestra un mensaje que no pueda conectarse a la libreta de direcciones. Para confirmar la conectividad de la libreta de direcciones, realice una búsqueda de un usuario en la barra de búsqueda de cliente de Skype Empresarial.

- Los problemas de replicación de AD DS podrían hacer que los contactos no se resuelvan cuando un usuario inicia sesión por primera vez en Skype Empresarial.