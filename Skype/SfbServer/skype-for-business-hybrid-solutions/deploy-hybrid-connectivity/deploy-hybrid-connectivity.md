---
title: Implementar conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
description: 'Resumen: Leer este tema para aprender a implementar conectividad híbrida entre Skype para Business Server y Skype para los negocios en línea.'
ms.openlocfilehash: 6dfe230088a2f3ecf827f3d8da9b6c9230ed4989
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>Implementar conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online
 
**Resumen:** lea este tema para aprender a implementar la conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online.
  
Antes de realizar los pasos de este tema, debería leer la [conectividad híbrida entre Skype para Business Server y Skype para los negocios en línea de Plan](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
  
Conectividad híbrida entre Skype para Business Server y Skype para los negocios en línea significa que los usuarios de un dominio, como contoso.com, se dividen entre el uso de Skype para Business Server en locales y Skype para los negocios en línea. Algunos usuarios del dominio están alojados en forma local, mientras que otros están en línea. 
  
La tabla siguiente enumeran los pasos necesarios para preparar su entorno para lograr una implementación híbrida con Skype para los negocios en línea y de Microsoft Office 365. 
  
|**Paso**|**Descripción**|
|:-----|:-----|
|Crear una cuenta de inquilinos para Office 365 y habilitar Skype para los negocios en línea  <br/> |Obtenga información acerca de Office 365 y Skype para el negocio en línea en [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Para asegurarse de que su entorno esté preparado para Office 365, consulte los [Requisitos del sistema](https://go.microsoft.com/fwlink/p/?LinkId=401408).  <br/> Para obtener más información acerca de cómo configurar Office 365, consulte [Introducción a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Agregue su dominio a los inquilinos de Office 365 y verificar la propiedad  <br/> | Agregue su dominio a su inquilino de Office 365 y después siga los pasos para validar el dominio con Office 365. Esto se hace para confirmar que usted es el propietario del dominio. <br/> Para agregar el dominio a los inquilinos de Office 365, siga los pasos descritos en [Agregar el dominio a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254983).  <br/> |
|Preparar para la sincronización de Active Directory  <br/> |Sincronización de Active Directory mantiene en instalaciones Active Directory continuamente sincronizado con Office 365. Esto le permite no solo crear versiones sincronizadas de cada grupo y cuenta de usuario, sino que también le permite la sincronización de la lista global de direcciones (GAL) desde su entorno de Microsoft Exchange Server local con Microsoft Exchange Online. Para obtener más información, vea [Herramientas de integración de directorio](https://go.microsoft.com/fwlink/p/?LinkId=530320).  <br/> > [!IMPORTANT]> Debe sincronizar las cuentas de AD para todos Skype para usuarios de negocio de la organización entre su local y de las implementaciones en línea, incluso si los usuarios no se mueven a Skype para los negocios en línea. Si no sincroniza todos los usuarios, puede ser que la comunicación entre los usuarios locales y en línea de su organización no funcione como se podría esperar.           |
|Mover los usuarios piloto  <br/> |Cuando haya completado los pasos necesarios para preparar y configurar su entorno para Skype para los negocios en línea, puede empezar a mover los usuarios piloto a su arrendatario en línea de Office 365. Consulte [mover usuarios desde en instalaciones a Skype para los negocios en línea](move-users-from-on-premises-to-skype-for-business-online.md).  <br/> |
|Administrar usuarios en una implementación híbrida  <br/> |Para obtener más información acerca de cómo administrar usuarios en una implementación híbrida, vea [Administrar usuarios en una implementación híbrida](http://technet.microsoft.com/library/6924ed7b-30a9-4be7-b952-90655625f2c8.aspx).  <br/> |
   

