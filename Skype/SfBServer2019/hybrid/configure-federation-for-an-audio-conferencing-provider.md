---
title: Configurar la federación para un proveedor de conferencias de audio en su implementación híbrida
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Resumen: Obtenga información sobre cómo configurar la federación para un proveedor de conferencias de audio en Skype para profesionales en línea.'
ms.openlocfilehash: 2f89045e7d2ee3e51a6526344d2dcf2f07c0d98d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030759"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurar la federación para un proveedor de conferencias de audio en su implementación híbrida

**Resumen:** Obtenga información sobre cómo configurar la federación para un proveedor de conferencias de audio en Skype para profesionales en línea.

Si desea usar un proveedor de audioconferencia (ACP) para la implementación híbrida (local con en línea), tiene que configurar la federación entre la implementación local y el asociado del ACP como servidor del asociado permitido. Para configurar la federación, agregue el dominio del asociado del ACP y el servidor perimetral (también se puede denominar servidor proxy de acceso) a la lista de dominios federados para la implementación local. Luego, su asociado del ACP tendrá que agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos. Póngase en contacto con su proveedor del ACP para más detalles. Su asociado del ACP tendrá que agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos.

- **Cómo agregar el dominio del ACP y el servidor perimetral como un dominio federado permitido**

    Para agregar el dominio ACP como un servidor de socio permitido (permitido dominio federado), siga los pasos de [Configuración de compatibilidad con dominios externos permitidos](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx). Para el servidor perimetral, agregue el FQDN del servidor perimetral del socio ACP. Puede que tenga que contactar con el asociado del ACP para obtener el FQDN del servidor perimetral, que el ACP también puede denominar servidor proxy de acceso.

- **Proporcionar el FQDN de su grupo de servidores perimetrales para el socio ACP**

    El asociado del ACP tiene que configurar la federación para agregar su dominio local como un servidor de asociado permitido agregando el FQDN de su grupo de servidores perimetrales como un dominio federado permitido.


