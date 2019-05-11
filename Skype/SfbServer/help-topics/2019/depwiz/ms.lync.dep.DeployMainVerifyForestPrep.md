---
title: Comprobar replicación de la preparación del bosque
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para confirmar que la replicación del catálogo Global y la creación de objetos durante la preparación del bosque se ha realizado correctamente, haga lo siguiente:'
ms.openlocfilehash: b755aeb6d7d9fe79940472b7b5883d1fdacaeee9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893626"
---
# <a name="verify-replication-of-forest-preparation"></a>Comprobar replicación de la preparación del bosque
 
Para confirmar que la replicación del catálogo Global y la creación de objetos durante la preparación del bosque se ha realizado correctamente, haga lo siguiente:
  
1. En un controlador de dominio (preferentemente en un sitio remoto desde otros controladores de dominio) en el bosque donde se ejecutó la preparación del bosque, abra **Usuarios y equipos de Active Directory**.
    
2. En **Usuarios y equipos de Active Directory**, expanda el nombre de dominio del bosque o un dominio secundario.
    
3. Haga clic en el contenedor de **usuarios** en el panel del lado izquierdo y busque el grupo Universal CsAdministrator en el panel del lado derecho. Si está presente CsAdministrator (entre ocho otros nuevos grupos universales que comienzan con Cs), la replicación de la preparación del bosque ha sido correcta.
    
4. Si aún no está presente el grupo o grupos, puede forzar la replicación o espere 15 minutos y actualizar el panel del lado derecho. Cuando los grupos están presentes, la replicación se ha completado.
    
> [!TIP]
> Si desea revisar los archivos de registro que se crean mediante la Skype para el Asistente para la implementación de Business Server, se puede encontrar en el equipo donde se ejecutó el Asistente para la implementación, en el directorio de usuarios del usuario de los servicios de dominio de Active Directory que se ejecutó el paso. Por ejemplo, si el usuario iniciado sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

