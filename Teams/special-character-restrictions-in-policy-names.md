---
title: ¿Cuáles son las restricciones de caracteres especiales en las directivas de los equipos?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: Vea ¿qué problemas hay con caracteres especiales en los nombres de las directivas y qué puede hacer para solucionarlo.
ms.openlocfilehash: 7d835669f0acc7cd2a2e42acb1aa9fa9d2fdf765
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205081"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>¿Cuáles son las restricciones de caracteres especiales en las directivas de los equipos?

**Aunque pueden usar caracteres especiales para la creación de directivas de los equipos con PowerShell, limitará en la administración de estas directivas.  Por lo tanto, se recomienda encarecidamente nombres de directiva no incluir caracteres especiales.**

Nombres de directiva que se crean con PowerShell para las reuniones y conversaciones en los equipos pueden tener caracteres especiales, como @, #, $. Sin embargo, si desea editar la directiva en el Microsoft Teams y Skype para el centro de administración de negocio, no podrá a. Debe usar Windows PowerShell y el cmdlet de directiva correcta para realizar cambios.

Si tiene un objeto de directiva con caracteres especiales y que desea quitar los caracteres especiales con el fin de administrar mejor la directiva en el Microsoft Teams y Skype para el centro de administración de negocio, debe usar el siguiente procedimiento. 

Nota: En el procedimiento articulado aquí se usa en el ejemplo de una directiva de mensajería.  Por subsituting los cmdlets relevantes, se usaría el mismo proceso para cualquier otro tipo de directiva (por ejemplo, las de reuniones). 

1.) llamar a Get-CSMessagingPolicy-identidad < antiguoNombreDeDirectiva > y captura el resultado de la directiva.
2.) llame a Set-CSMessagingPolicy-identidad < nuevoNombreDeDirectiva > para crear una nueva directiva con la misma configuración que la directiva original pero sin caracteres especiales en el nombre.
3.) llamar a Delete-CSMessagingPolicy-identidad < antiguoNombreDeDirectiva > para eliminar la directiva.  Si este comando se ejecuta correctamente, se hayan acabado y puede empezar a asignar a los usuarios a la nueva directiva de uso de PowerShell o el Microsoft Teams y Skype para el centro de administración de negocio.
4.) si el comando anterior no se realiza correctamente, es debido a que se ha asignado la directiva anterior a un usuario.  Ejecutar cancelar la asignación de cmdlet para quitar la asignación de la directiva de usuario, asignar la nueva directiva y, a continuación, vuelva a ejecutar dwlete.


