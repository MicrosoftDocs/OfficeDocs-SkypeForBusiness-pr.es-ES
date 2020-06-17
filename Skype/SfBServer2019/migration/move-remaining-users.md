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
description: 'Puede mover usuarios a la nueva implementación de Skype empresarial Server 2019 mediante el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial Server. Debe cumplir algunos requisitos para garantizar una transición sin problemas a Skype empresarial Server 2019. Para obtener más información sobre los requisitos previos para completar los procedimientos de este tema, vea configure clients for Migration. Para obtener instrucciones detalladas sobre cómo mover usuarios, consulte Phase 4: Move test users to the Pilot Pool.'
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753718"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Mover los usuarios restantes a Skype empresarial Server 2019

Puede mover usuarios a la nueva implementación de Skype empresarial Server 2019 mediante el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial Server. Debe cumplir algunos requisitos para garantizar una transición sin problemas a Skype empresarial Server 2019. Para obtener más información sobre los requisitos previos para completar los procedimientos de este tema, vea [Configure clients for Migration](configure-clients-for-migration.md). Para obtener instrucciones detalladas sobre cómo mover usuarios, consulte [Phase 4: Move test users to the Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md).
  
> [!IMPORTANT]
> No puede usar el complemento usuarios y equipos de Active Directory ni las herramientas administrativas heredadas para mover usuarios de su entorno heredado a Skype empresarial Server 2019. 
  
Al mover un usuario a un grupo de servidores de Skype empresarial Server 2019, los datos del usuario se mueven a la base de datos back-end asociada al nuevo grupo. 
  
> [!IMPORTANT]
> Estos datos incluyen las reuniones activas creadas por el usuario heredado. Por ejemplo, si un usuario heredado ha configurado una conferencia de **mi reunión** , dicha conferencia seguirá disponible en el nuevo grupo de servidores de Skype empresarial Server 2019 después de que se haya movido al usuario. Los datos de acceso de esa reunión continuarán siendo los mismos **URL de conferencia e ID de conferencia**. La única diferencia es que la Conferencia ahora está hospedada en el grupo de Skype empresarial Server 2019 y no en el grupo de servidores heredados. 
  
> [!NOTE]
> El alojamiento de usuarios en Skype empresarial Server 2019 no requiere que se implementen clientes actualizados al mismo tiempo. La funcionalidad nueva estará disponible para los usuarios únicamente cuando hayan actualizado al nuevo software cliente. 
  
### <a name="post-migration-task"></a>Tarea posterior a la migración

1. Tras migrar los usuarios, compruebe la directiva de conferencia que tienen asignada. 
    
2. Para asegurarse de que las reuniones organizadas por usuarios hospedados en Skype empresarial Server 2019 funcionan sin problemas con los usuarios federados hospedados en una instalación heredada, la Directiva de conferencia asignada a los usuarios migrados debe permitir los participantes anónimos.
    
3. Las directivas de conferencia que permiten a los participantes anónimos **permiten a los participantes invitar a usuarios anónimos** seleccionados en el panel de control de Skype empresarial Server 2019 y tienen **AllowAnonymousParticipantsInMeetings** establecido en **true** en el resultado del cmdlet **Get-CsConferencingPolicy** en el shell de administración de Skype empresarial Server. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

