---
title: Preparar Active Directory
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Para comenzar la instalación de Skype Empresarial Server 2015, debe preparar el esquema, el bosque y los dominios de servicios de dominio de Active Directory que hospedarán servidores y usuarios. El Skype Empresarial Server de implementación le guiará a través de los pasos necesarios para preparar Active Directory, empezando por el esquema y, a continuación, en la preparación del bosque. Después de confirmar que la replicación de Active Directory se realiza correctamente, debe preparar cada dominio que hospedará usuarios o servidores.
ms.openlocfilehash: 5882a9f016590b7e821f061d2a9db0e38ef2ab35
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843083"
---
# <a name="prepare-active-directory"></a>Preparar Active Directory

Para comenzar la instalación de Skype Empresarial Server 2015, debe preparar el esquema, el bosque y los dominios de servicios de dominio de Active Directory que hospedarán servidores y usuarios. El Skype Empresarial Server de implementación le guiará a través de los pasos necesarios para preparar Active Directory, empezando por el esquema y, a continuación, en la preparación del bosque. Después de confirmar que la replicación de Active Directory se realiza correctamente, debe preparar cada dominio que hospedará usuarios o servidores.

> [!IMPORTANT]
> Para preparar el esquema correctamente, debe iniciar sesión como miembro de los grupos Administradores de esquema y Administradores de organización. Para preparar el bosque, debe iniciar sesión como miembro del grupo Administradores de organización o como administrador en el dominio raíz del bosque. Para la preparación del dominio, debe iniciar sesión como miembro del grupo Admins. del dominio.

Para información detallada sobre las topologías de Active Directory admitidas, vea [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) en la documentación sobre compatibilidad. Para información detallada sobre la preparación de Active Directory, vea [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) en la documentación sobre implementación.