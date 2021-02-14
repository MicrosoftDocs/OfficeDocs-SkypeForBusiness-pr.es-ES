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
description: 'Puede mover usuarios a la nueva implementación de Skype Empresarial Server 2019 mediante el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server. Debe cumplir algunos requisitos para garantizar una transición sin problemas a Skype Empresarial Server 2019. Para obtener más información acerca de los requisitos previos para completar los procedimientos de este tema, vea Configurar clientes para la migración. Para obtener instrucciones detalladas sobre cómo mover usuarios, consulte Fase 4: Mover usuarios de prueba al grupo piloto.'
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753718"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Mover los usuarios restantes a Skype Empresarial Server 2019

Puede mover usuarios a la nueva implementación de Skype Empresarial Server 2019 mediante el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server. Debe cumplir algunos requisitos para garantizar una transición sin problemas a Skype Empresarial Server 2019. Para obtener más información sobre los requisitos previos para completar los procedimientos de este tema, vea [Configurar clientes para la migración.](configure-clients-for-migration.md) Para obtener instrucciones detalladas sobre cómo mover usuarios, vea [fase 4:](phase-4-move-test-users-to-the-pilot-pool.md)Mover usuarios de prueba al grupo piloto.
  
> [!IMPORTANT]
> No puede usar el complemento Usuarios y equipos de Active Directory ni las herramientas administrativas heredadas para mover usuarios de su entorno heredado a Skype Empresarial Server 2019. 
  
Cuando mueve un usuario a un grupo de Skype Empresarial Server 2019, los datos del usuario se mueven a la base de datos back-end asociada con el nuevo grupo. 
  
> [!IMPORTANT]
> Estos datos incluyen las reuniones activas creadas por el usuario heredado. Por ejemplo, si un usuario  heredado ha configurado una conferencia de mi reunión, esa conferencia seguirá estando disponible en el nuevo grupo de Skype Empresarial Server 2019 después de que se haya movido el usuario. Los datos de acceso de esa reunión continuarán siendo los mismos **URL de conferencia e ID de conferencia**. La única diferencia es que la conferencia ahora se hospeda en el grupo de Skype Empresarial Server 2019 y no en el grupo heredado. 
  
> [!NOTE]
> No es necesario que implemente clientes actualizados al mismo tiempo en Skype Empresarial Server 2019. La funcionalidad nueva estará disponible para los usuarios únicamente cuando hayan actualizado al nuevo software cliente. 
  
### <a name="post-migration-task"></a>Tarea posterior a la migración

1. Tras migrar los usuarios, compruebe la directiva de conferencia que tienen asignada. 
    
2. Para asegurarse de que las reuniones organizadas por usuarios que se encuentran en Skype Empresarial Server 2019 funcionan sin problemas con los usuarios federados que se encuentran en una instalación heredada, la directiva de conferencia asignada a los usuarios migrados debe permitir participantes anónimos.
    
3. Las directivas de conferencia que permiten a los **participantes anónimos** permiten a los participantes invitar a usuarios anónimos seleccionados en el Panel de control de Skype Empresarial Server 2019 y tienen **AllowAnonymousParticipantsInMeetings** establecido en **True** en el resultado del cmdlet **Get-CsConferencingPolicy** en el Shell de administración de Skype Empresarial Server. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

