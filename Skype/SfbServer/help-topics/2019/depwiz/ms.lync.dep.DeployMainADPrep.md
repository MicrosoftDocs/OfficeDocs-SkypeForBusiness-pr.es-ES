---
title: Preparar Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: Para comenzar la instalación de Skype Empresarial Server, debe preparar el esquema, el bosque y los dominios de Servicios de dominio de Active Directory que hospedarán servidores y usuarios. El Asistente para la implementación de Skype Empresarial Server le guiará a través de los pasos necesarios para preparar Active Directory, comenzando por el esquema y, a continuación, en la preparación del bosque. Después de confirmar que la replicación de Active Directory se realiza correctamente, prepare cada dominio que hospedará usuarios o servidores.
ms.openlocfilehash: 4e2951643ddc0f569df6802b6ff5fdd8d2c12a82
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825057"
---
# <a name="prepare-active-directory"></a>Preparar Active Directory

Para comenzar la instalación de Skype Empresarial Server, debe preparar el esquema, el bosque y los dominios de Servicios de dominio de Active Directory que hospedarán servidores y usuarios. El Asistente para la implementación de Skype Empresarial Server le guiará a través de los pasos necesarios para preparar Active Directory, comenzando por el esquema y, a continuación, en la preparación del bosque. Después de confirmar que la replicación de Active Directory se realiza correctamente, prepare cada dominio que hospedará usuarios o servidores.

> [!IMPORTANT]
> Para preparar el esquema correctamente, debe iniciar sesión como miembro de los grupos Administradores de esquema y Administradores de organización. Para preparar el bosque, debe iniciar sesión como miembro del grupo Administradores de organización o como administrador en el dominio raíz del bosque. Para la preparación del dominio, debe iniciar sesión como miembro del grupo Admins. del dominio.

Para información detallada sobre las topologías de Active Directory admitidas, vea [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) en la documentación sobre compatibilidad. Para información detallada sobre la preparación de Active Directory, vea [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) en la documentación sobre implementación.


