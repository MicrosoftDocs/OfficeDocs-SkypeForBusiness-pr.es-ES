---
title: Preparar Active Directory
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: Para comenzar la instalación de Skype Empresarial Server, debe preparar el esquema, el bosque y los dominios de servicios de dominio de Active Directory que hospedarán servidores y usuarios. El Skype Empresarial Server de implementación le guiará a través de los pasos necesarios para preparar Active Directory, empezando por el esquema y, a continuación, en la preparación del bosque. Después de confirmar que la replicación de Active Directory se realiza correctamente, debe preparar cada dominio que hospedará usuarios o servidores.
ms.openlocfilehash: c8973d9f5e269a9ebea48c81c70e68d74759eb92
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60755333"
---
# <a name="prepare-active-directory"></a>Preparar Active Directory

Para comenzar la instalación de Skype Empresarial Server, debe preparar el esquema, el bosque y los dominios de servicios de dominio de Active Directory que hospedarán servidores y usuarios. El Skype Empresarial Server de implementación le guiará a través de los pasos necesarios para preparar Active Directory, empezando por el esquema y, a continuación, en la preparación del bosque. Después de confirmar que la replicación de Active Directory se realiza correctamente, debe preparar cada dominio que hospedará usuarios o servidores.

> [!IMPORTANT]
> Para preparar el esquema correctamente, debe iniciar sesión como miembro de los grupos Administradores de esquema y Administradores de organización. Para preparar el bosque, debe iniciar sesión como miembro del grupo Administradores de organización o como administrador en el dominio raíz del bosque. Para la preparación del dominio, debe iniciar sesión como miembro del grupo Admins. del dominio.

Para información detallada sobre las topologías de Active Directory admitidas, vea [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) en la documentación sobre compatibilidad. Para información detallada sobre la preparación de Active Directory, vea [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) en la documentación sobre implementación.