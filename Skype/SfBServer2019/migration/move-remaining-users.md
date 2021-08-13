---
title: Mover el resto de usuarios
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
description: 'Puede mover usuarios a la nueva implementación Skype Empresarial Server 2019 con el Panel de control Skype Empresarial Server o el Shell Skype Empresarial Server administración. Debe cumplir algunos requisitos para garantizar una transición sin problemas a Skype Empresarial Server 2019. Para obtener información detallada sobre los requisitos previos para completar los procedimientos de este tema, vea Configure clients for migration. Para obtener instrucciones detalladas sobre cómo mover usuarios, vea Fase 4: Mover usuarios de prueba al grupo piloto.'
ms.openlocfilehash: a2742acf32899aca71c28da733c723640a8c1e9200f26f793a918eac04714f15
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300636"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Mover los usuarios restantes a Skype Empresarial Server 2019

Puede mover usuarios a la nueva implementación Skype Empresarial Server 2019 con el Panel de control Skype Empresarial Server o el Shell Skype Empresarial Server administración. Debe cumplir algunos requisitos para garantizar una transición sin problemas a Skype Empresarial Server 2019. Para obtener más información sobre los requisitos previos para completar los procedimientos de este tema, vea [Configure clients for migration](configure-clients-for-migration.md). Para obtener instrucciones detalladas sobre cómo mover usuarios, vea [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).
  
> [!IMPORTANT]
> No puede usar el complemento Usuarios y equipos de Active Directory ni las herramientas administrativas heredadas para mover usuarios de su entorno heredado a Skype Empresarial Server 2019. 
  
Al mover un usuario a un grupo de servidores de Skype Empresarial Server 2019, los datos del usuario se mueven a la base de datos back-end asociada al nuevo grupo. 
  
> [!IMPORTANT]
> Estos datos incluyen las reuniones activas creadas por el usuario heredado. Por ejemplo, si un usuario  heredado ha configurado una conferencia de mi reunión, esa conferencia seguirá estando disponible en el nuevo grupo de servidores de Skype Empresarial Server 2019 después de que se haya movido el usuario. Los datos de acceso de esa reunión continuarán siendo los mismos **URL de conferencia e ID de conferencia**. La única diferencia es que la conferencia se hospeda ahora en el grupo Skype Empresarial Server 2019 y no en el grupo heredado. 
  
> [!NOTE]
> La asociación de usuarios Skype Empresarial Server 2019 no requiere que implemente clientes actualizados al mismo tiempo. La funcionalidad nueva estará disponible para los usuarios únicamente cuando hayan actualizado al nuevo software cliente. 
  
### <a name="post-migration-task"></a>Tarea posterior a la migración

1. Tras migrar los usuarios, compruebe la directiva de conferencia que tienen asignada. 
    
2. Para asegurarse de que las reuniones organizadas por los usuarios en Skype Empresarial Server 2019 funcionan sin problemas con los usuarios federados que se encuentran en la instalación heredada, la directiva de conferencia asignada a los usuarios migrados debe permitir a los participantes anónimos.
    
3. Las directivas de conferencia que permiten Skype Empresarial Server los **participantes anónimos** invitar a usuarios anónimos seleccionados en el Panel de control de Skype Empresarial Server 2019 y tienen **AllowAnonymousParticipantsInMeetings** establecido en **True** en el resultado del cmdlet **Get-CsConferencingPolicy** en el Shell de administración de Skype Empresarial Server. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

