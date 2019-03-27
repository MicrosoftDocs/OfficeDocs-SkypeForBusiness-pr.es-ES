---
title: Mover al resto de los usuarios
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Puede mover usuarios a la nueva Skype para la implementación empresarial Server 2019 mediante cualquiera Skype para Panel de Control de servidor empresarial o Skype para Shell de administración de servidor empresarial. Deben cumplir algunos requisitos para garantizar una transición sin problemas a Skype para Business Server 2019. Para obtener información detallada sobre los requisitos previos para completar los procedimientos descritos en este tema, vea a configurar clientes para la migración. Para los pasos detallados sobre cómo mover usuarios, vea fase 4: mover usuarios de prueba al grupo piloto.'
ms.openlocfilehash: 9f984b7fac919decce521c6dafc587a4ac86de50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878328"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Mover el resto de usuarios a Skype para Business Server 2019

Puede mover usuarios a la nueva Skype para la implementación empresarial Server 2019 mediante cualquiera Skype para Panel de Control de servidor empresarial o Skype para Shell de administración de servidor empresarial. Deben cumplir algunos requisitos para garantizar una transición sin problemas a Skype para Business Server 2019. Para obtener información detallada sobre los requisitos previos para completar los procedimientos descritos en este tema, vea [Configurar clientes para la migración](configure-clients-for-migration.md). Para obtener instrucciones detalladas sobre cómo mover usuarios, vea [fase 4: mover usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md).
  
> [!IMPORTANT]
> No puede usar el complemento Usuarios y equipos de usuarios de Active Directory o las herramientas administrativas de heredado para mover los usuarios del entorno heredado a Skype para Business Server 2019. 
  
Cuando un usuario se mueve a un Skype para Business Server 2019 grupo, los datos para el usuario se mueven a la base de datos back-end que está asociada con el nuevo grupo de servidores. 
  
> [!IMPORTANT]
> Esto incluye las reuniones activas creadas por el usuario heredado. Por ejemplo, si un usuario heredado ha configurado una conferencia de **Mi reunión** , esa conferencia aún estará disponible en el nuevo Skype para Business Server 2019 grupo después de que el usuario se ha movido. Los detalles para tener acceso a dicha reunión seguirá siendo la misma **dirección URL de conferencia y el identificador de conferencia**. La única diferencia es que la conferencia ahora está hospedada en el Skype para Business Server 2019 grupo y no en el grupo heredado. 
  
> [!NOTE]
> Hospedar los usuarios de Skype para Business Server 2019 no requiere que implementar los clientes actualizados al mismo tiempo. Nueva funcionalidad estará disponible para los usuarios sólo cuando se ha actualizado para el nuevo software de cliente. 
  
### <a name="post-migration-task"></a>Tarea posterior a la migración

1. Después de mover usuarios, compruebe la directiva de conferencia que se les haya asignado. 
    
2. Para garantizar que las reuniones organizadas por los usuarios hospedados en Skype para el trabajo de Business Server 2019 sin problemas con los usuarios federados que están hospedados en install heredado, la directiva de conferencia asignada a los usuarios migrados debe permitir a participantes anónimos.
    
3. Las directivas de conferencia que permiten participantes anónimos tienen seleccionada en Skype para el Panel de Control de Business Server 2019 de **Permitir que los participantes invitar a usuarios anónimos** y tienen la **opción AllowAnonymousParticipantsInMeetings** establecen en **True** en el resultado desde el cmdlet **Get-CsConferencingPolicy** en la Skype para Shell de administración de servidor empresarial. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

