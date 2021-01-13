---
title: Comprobar replicación de la preparación del bosque
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para confirmar que la replicación del catálogo global y la creación de objetos durante la preparación del bosque se han realizado correctamente, siga estos pasos:'
ms.openlocfilehash: 299b738bbfa14ad13825e5c08e87c03167c9f4cc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801600"
---
# <a name="verify-replication-of-forest-preparation"></a>Comprobar replicación de la preparación del bosque
 
Para confirmar que la replicación del catálogo global y la creación de objetos durante la preparación del bosque se han realizado correctamente, siga estos pasos:
  
1. En un controlador de dominio (preferiblemente en un sitio remoto desde otros controladores de dominio) del bosque en el que se ejecutó la preparación del bosque, abra  **Usuarios y equipos de Active Directory**.
    
2. En  **Usuarios y equipos de Active Directory**, expanda el nombre de dominio del bosque o un dominio secundario.
    
3. Haga clic **en el** contenedor Usuarios del panel izquierdo y busque el grupo universal CsAdministrator en el panel derecho. Si CsAdministrator (entre otros ocho nuevos grupos universales que comienzan con Cs) está presente, la replicación de la preparación del bosque se ha realizado correctamente.
    
4. Si el grupo o los grupos aún no están presentes, puede forzar la replicación o esperar 15 minutos y actualizar el panel derecho. Cuando los grupos están presentes, la replicación se ha completado.
    
> [!TIP]
> Si desea revisar los archivos de registro creados por el Asistente para la implementación de Skype Empresarial Server, puede encontrarlos en el equipo donde se ejecutó el Asistente para la implementación, en el directorio de usuarios del usuario de Servicios de dominio de Active Directory que realizó el paso. Por ejemplo, si el usuario inició sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

