---
title: Preparar un servidor único de Standard Edition (introducción)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: Para comenzar la instalación de un servidor de Skype Empresarial Server Standard Edition que hospedará el almacén de administración central y otros servicios agrupados que seleccione, debe haber iniciado sesión como miembro del grupo administradores local en el servidor que se convertirá en el servidor Standard Edition. En la página de preparación de un solo servidor Standard Edition se detallan los requisitos para la instalación inicial. El equipo debe ser miembro del dominio en el que se va a implementar, y el usuario debe haber completado correctamente la preparación del esquema, el bosque y el dominio para el bosque.
ms.openlocfilehash: 352b4ece936d609ed73540370313d21e83b9034c5efdbbdefb40528921bf8e34
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54292248"
---
# <a name="prepare-single-standard-edition-server-intro"></a>Preparar un servidor único de Standard Edition (introducción)
 
Para comenzar la instalación de un servidor de Skype Empresarial Server Standard Edition que hospedará el almacén de administración central y otros servicios agrupados que seleccione, debe haber iniciado sesión como miembro del grupo administradores local en el servidor que se convertirá en el servidor Standard Edition. En la página de **preparación de un solo servidor Standard Edition** se detallan los requisitos para la instalación inicial. El equipo debe ser miembro del dominio en el que se va a implementar, y el usuario debe haber completado correctamente la preparación del esquema, el bosque y el dominio para el bosque.
  
El objetivo de esta tarea específica es configurar un servidor Standard Edition como primer servidor de la infraestructura. Esta tarea instala el almacén de administración central, que SQL Server Express, en el Standard Edition servidor. Si ya tiene implementado otro servidor Standard Edition u otro grupo de servidores front-end, debe hacer clic en **Cancelar**.
  
> [!NOTE]
> Después de completar esta tarea, instalará el Generador de topologías (si aún no lo ha instalado) y configurará el documento de topología. No podrá publicar el documento de topología hasta que tenga un almacén de administración central disponible, que se implementa completando la tarea descrita en este tema. 
  

