---
title: Mover al resto de los usuarios
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Puede mover usuarios a la nueva implementación de Skype empresarial Server 2019 con el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial. Debe cumplir algunos requisitos para garantizar una transición sin problemas a Skype empresarial Server 2019. Para obtener más información sobre los requisitos previos para completar los procedimientos de este tema, vea Configurar clientes para la migración. Para conocer los pasos detallados sobre cómo mover usuarios, consulte la fase 4: mover usuarios de prueba a la agrupación piloto.'
ms.openlocfilehash: 8c12ca52e162c4317dabc59d5de9b74082730882
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244568"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Mover los usuarios restantes a Skype empresarial Server 2019

Puede mover usuarios a la nueva implementación de Skype empresarial Server 2019 con el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial. Debe cumplir algunos requisitos para garantizar una transición sin problemas a Skype empresarial Server 2019. Para obtener más información sobre los requisitos previos para completar los procedimientos de este tema, vea [configurar clientes para la migración](configure-clients-for-migration.md). Para conocer los pasos detallados sobre cómo mover usuarios, consulte [la fase 4: mover usuarios de prueba a la agrupación piloto](phase-4-move-test-users-to-the-pilot-pool.md).
  
> [!IMPORTANT]
> No puede usar el complemento usuarios y equipos de Active Directory ni las herramientas administrativas heredadas para mover usuarios de su entorno heredado a Skype empresarial Server 2019. 
  
Al mover un usuario a un grupo de servidores de Skype empresarial 2019, los datos del usuario se mueven a la base de datos back-end asociada con el nuevo grupo. 
  
> [!IMPORTANT]
> Esto incluye las reuniones activas creadas por el usuario heredado. Por ejemplo, si un usuario heredado ha configurado una conferencia de **reunión** , dicha conferencia seguirá estando disponible en el nuevo grupo de servidores de Skype empresarial 2019 después de que se haya movido al usuario. Los detalles para acceder a la reunión seguirán siendo la misma **dirección URL de conferencia y**el mismo identificador de conferencia. La única diferencia es que la Conferencia ahora está hospedada en el grupo de servidores de Skype empresarial 2019, y no en el grupo heredado. 
  
> [!NOTE]
> El alojamiento de usuarios en Skype empresarial Server 2019 no requiere que implemente clientes actualizados al mismo tiempo. Las nuevas funcionalidades estarán disponibles solo para los usuarios cuando se actualicen al nuevo software de cliente. 
  
### <a name="post-migration-task"></a>Tarea posterior a la migración

1. Después de mover usuarios, Compruebe la Directiva de conferencia que tiene asignada. 
    
2. Para asegurarse de que las reuniones organizadas por usuarios alojados en Skype empresarial Server 2019 funcionen sin problemas con usuarios federados que estén alojados en una instalación heredada, la Directiva de conferencia asignada a los usuarios migrados debe permitir participantes anónimos.
    
3. Las directivas de conferencia que permiten a los participantes anónimos **permiten a los participantes invitar a usuarios anónimos** seleccionados en el panel de control de Skype empresarial Server 2019 y tienen **AllowAnonymousParticipantsInMeetings** establecido en **verdadero** en el salida del cmdlet **Get-CsConferencingPolicy** en el shell de administración de Skype empresarial Server. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

