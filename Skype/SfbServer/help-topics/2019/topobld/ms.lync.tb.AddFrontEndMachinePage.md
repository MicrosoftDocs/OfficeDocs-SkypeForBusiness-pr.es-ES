---
title: Agregar equipo front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: Especifique el nombre de dominio completo (FQDN) de cada equipo que desea agregar como un servidor Front-End de este grupo. Tras haber agregado un equipo a la lista, puede actualizar el nombre de dominio completo del equipo o quitarlo del grupo de servidores en cualquier momento antes de publicar la topología. Después de publicar la topología, el cambio del FQDN requiere eliminar el servidor en el generador de topología y, a continuación, agregar un nuevo servidor al grupo de servidores con el FQDN nuevo. Para obtener información detallada sobre cómo agregar un grupo de servidores Front-End a la topología, consulte definir y configurar un grupo de servidores Front-End en la documentación de implementación.
ms.openlocfilehash: 321e1f392fb06ba4e99dc17e668e188b2fee5338
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33912067"
---
# <a name="add-front-end-machine"></a>Agregar equipo front-end

Especifique el nombre de dominio completo (FQDN) de cada equipo que desea agregar como un servidor Front-End de este grupo. Tras haber agregado un equipo a la lista, puede actualizar el nombre de dominio completo del equipo o quitarlo del grupo de servidores en cualquier momento antes de publicar la topología. Después de publicar la topología, el cambio del FQDN requiere eliminar el servidor en el generador de topología y, a continuación, agregar un nuevo servidor al grupo de servidores con el FQDN nuevo. Para obtener información detallada sobre cómo agregar un grupo de servidores Front-End a la topología, consulte [definir y configurar un grupo de servidores Front-End](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) en la documentación de implementación.

> [!IMPORTANT]
> Tenga en cuenta que el generador de topología indica que puede tener un máximo de 20 servidores Front-End en un grupo de servidores. El número máximo admitido de servidores es 12. Puede tener un máximo de 20 servidores de estado definidos en el fabric, de los cuales 12 puede ser activa y en línea en cualquier momento.


