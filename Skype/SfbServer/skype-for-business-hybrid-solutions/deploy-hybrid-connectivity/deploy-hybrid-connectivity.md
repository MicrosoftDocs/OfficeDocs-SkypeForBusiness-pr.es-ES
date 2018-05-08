---
title: Implementar conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
description: 'Resumen: Lea este tema para obtener información sobre cómo implementar conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea.'
ms.openlocfilehash: d96cff493daf8efa213c635a5a1454bfa370de9a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>Implementar conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online
 
**Resumen:** lea este tema para aprender a implementar la conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online.
  
Antes de llevar a cabo los pasos de este tema, debe leer la [planeación de la conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
  
Conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea significa que los usuarios de un dominio, como contoso.com, se reparten entre el uso de Skype para Business Server local y Skype para profesionales en línea. Algunos usuarios del dominio están alojados en forma local, mientras que otros están en línea. 
  
En la siguiente tabla se enumera los pasos necesarios para preparar su entorno para una implementación híbrida con Skype para profesionales en línea y Microsoft Office 365. 
  
|**Paso**|**Descripción**|
|:-----|:-----|
|Crear una cuenta del inquilino para Office 365 y habilitar Skype para profesionales en línea  <br/> |Obtenga información acerca de Office 365 y Skype para la empresa en línea en [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Para asegurarse de que su entorno está preparado para Office 365, vea los [Requisitos del sistema](https://go.microsoft.com/fwlink/p/?LinkId=401408).  <br/> Para obtener información detallada sobre cómo configurar Office 365, vea [Introducción a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Agregue su dominio a su inquilino Office 365 y compruebe la propiedad  <br/> | Agregue su dominio a su inquilino de Office 365 y después siga los pasos para validar el dominio con Office 365. Esto se hace para confirmar que usted es el propietario del dominio. <br/> Para agregar su dominio a su inquilino de Office 365, siga los pasos descritos en [Agregar un dominio a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254983).  <br/> |
|Preparación para la sincronización de Active Directory  <br/> |Sincronización de Active Directory mantiene su Active Directory local sincronizado continuamente con Office 365. Esto le permite no solo crear versiones sincronizadas de cada grupo y cuenta de usuario, sino que también le permite la sincronización de la lista global de direcciones (GAL) desde su entorno de Microsoft Exchange Server local con Microsoft Exchange Online. Para obtener más información, vea [Herramientas de integración de Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=530320).  <br/> > [!IMPORTANT]> Debe sincronizar las cuentas de AD para todos los Skype para usuarios profesionales de la organización entre la organización local y en línea de las implementaciones, incluso si los usuarios no se mueven a Skype para profesionales en línea. Si no sincroniza todos los usuarios, puede ser que la comunicación entre los usuarios locales y en línea de su organización no funcione como se podría esperar.           |
|Mover los usuarios piloto  <br/> |Después de haber completado los pasos necesarios para preparar y configurar el entorno de Skype para profesionales en línea, puede empezar a mover los usuarios pilotos a su inquilino de Office 365 en línea. Consulte [mover usuarios de local a Skype para profesionales en línea](move-users-from-on-premises-to-skype-for-business-online.md).  <br/> |
|Administrar usuarios en una implementación híbrida  <br/> |Para obtener información detallada acerca de cómo administrar usuarios en una implementación híbrida, consulte [Administering a los usuarios en una implementación híbrida](http://technet.microsoft.com/library/6924ed7b-30a9-4be7-b952-90655625f2c8.aspx).  <br/> |
   

