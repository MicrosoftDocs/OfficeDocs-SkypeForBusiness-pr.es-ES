---
title: Configurar conectividad híbrida
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instrucciones para implementar la conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea.
ms.openlocfilehash: 2f14859e600a06a57b67a14249e954f3e4e6d4a2
ms.sourcegitcommit: a54864c3fcd1b8d240d0f7f2ccf68f8cba566e47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2018
ms.locfileid: "25849358"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Configurar la conectividad híbrida entre Skype para Business Server y Office 365
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar la conectividad híbrida entre Skype para Business Server y los equipos o Skype para profesionales en línea.  Conectividad híbrida permite mover los usuarios locales a los equipos o Skype para profesionales en línea y permite a los usuarios a aprovechar las ventajas de los servicios de nube.
  
Antes de llevar a cabo los pasos de este tema, debe leer la [planeación de la conectividad híbrida entre Skype para Business Server y Office 365](plan-hybrid-connectivity.md).
  
En la siguiente tabla se enumera las tareas necesarias para configurar Skype para la conectividad híbrida de negocio y proporciona vínculos a los artículos asociados para obtener más información.
  
|**Paso**|**Descripción**|
|:-----|:-----|
|Crear una cuenta del inquilino de Office 365   <br/> |Obtenga información acerca de Office 365 en [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Para asegurarse de que su entorno está preparado para Office 365, vea los [Requisitos del sistema](https://products.office.com/en-US/office-system-requirements).  <br/> Para más información sobre la configuración de Office 365, vea [Introducción a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Agregue su dominio a su inquilino Office 365 y compruebe la propiedad  <br/> | Agregue su dominio a su inquilino de Office 365 y después siga los pasos para validar el dominio con Office 365. Esto se hace para confirmar que usted es el propietario del dominio. <br/> Para agregar su dominio a su inquilino de Office 365, siga los pasos descritos en [Agregar un dominio a Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Configurar la sincronización de Active Directory  <br/> |Sincronización de Active Directory mantiene su Active Directory local sincronizado continuamente con Office 365. Esto le permite crear versiones sincronizadas de cada cuenta de usuario y grupo.  <br/> <br> **Importante:** Debe sincronizar las cuentas de AD para todos los Skype para usuarios profesionales de la organización entre la organización local y en línea de las implementaciones, incluso si los usuarios no se mueven a los equipos o Skype para profesionales en línea. Si no sincroniza todos los usuarios, puede que la comunicación entre los usuarios locales y en línea de su organización no funcione como es de esperar. Para obtener más información, vea [Configurar Azure AD conectar para entornos híbridos](configure-azure-ad-connect.md).         |
| Configuración de Skype para entornos híbridos de negocio | Hay tres pasos básicos: <br><br> 1. configurar su entorno local para federar con Office 365. <br> 2. configurar su entorno local para que confíe en Office 365 y habilite el espacio de direcciones SIP compartido con Office 365.<br> 3. habilitar el espacio de direcciones SIP compartido en el inquilino de Office 365. <br><br> Además, si dispone de Exchange local, es posible que desee configurar OAuth entre la organización local de Exchange y Skype para entornos en línea de negocio. <br> <br>Para obtener más información, vea [Configurar Skype para entornos híbridos de negocio](configure-federation-with-skype-for-business-online.md).
|Mover los usuarios piloto  <br/> |Después de haber completado los pasos necesarios para preparar y configurar el entorno para los equipos o Skype para profesionales en línea, puede empezar a mover los usuarios pilotos a su inquilino de Office 365 en línea. Para obtener más información, vea [mover usuarios de local a Skype para profesionales en línea](move-users-from-on-premises-to-skype-for-business-online.md) y [mover los usuarios de local a los equipos](move-users-from-on-premises-to-Teams.md).  <br/> | 

  