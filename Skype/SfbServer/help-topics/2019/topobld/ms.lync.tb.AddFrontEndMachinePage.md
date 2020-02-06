---
title: Agregar equipo front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: Especifique el nombre de dominio completo (FQDN) de cada equipo que quiera agregar como servidor front-end en este grupo. Tras haber agregado un equipo a la lista, puede actualizar el nombre de dominio completo del equipo o quitarlo del grupo de servidores en cualquier momento antes de publicar la topología. Después de publicar la topología, cambiar el FQDN requiere que se elimine el servidor en el generador de topología y que, después, se agregue un nuevo servidor al grupo con el nuevo FQDN. Para obtener más información sobre cómo agregar un grupo de servidores front-end a la topología, vea definir y configurar un grupo de servidores front-end en la documentación de implementación.
ms.openlocfilehash: a4ff4ce7a7fc775e33657dc2f8602d62163ed1d4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798547"
---
# <a name="add-front-end-machine"></a>Agregar equipo front-end

Especifique el nombre de dominio completo (FQDN) de cada equipo que quiera agregar como servidor front-end en este grupo. Tras haber agregado un equipo a la lista, puede actualizar el nombre de dominio completo del equipo o quitarlo del grupo de servidores en cualquier momento antes de publicar la topología. Después de publicar la topología, cambiar el FQDN requiere que se elimine el servidor en el generador de topología y que, después, se agregue un nuevo servidor al grupo con el nuevo FQDN. Para obtener más información sobre cómo agregar un grupo de servidores front-end a la topología, vea [definir y configurar un grupo de servidores front-end](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) en la documentación de implementación.

> [!IMPORTANT]
> Tenga en cuenta que el generador de topología indica que puede tener hasta 20 servidores front-end en un grupo. El número máximo admitido de servidores es de 12. Puede tener hasta 20 servidores statefull definidos en el tejido, de los cuales 12 puede estar activo y conectado en cualquier momento.


