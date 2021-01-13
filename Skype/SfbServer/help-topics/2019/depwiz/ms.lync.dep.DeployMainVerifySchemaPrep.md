---
title: Comprobar la replicación de la partición del esquema
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para comprobar que la extensión de esquema se haya replicado correctamente en el bosque de Servicios de dominio de Active Directory, haga lo siguiente:'
ms.openlocfilehash: 4e4bfdf4fb50366f831f029d8f331551ba906969
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801570"
---
# <a name="verify-replication-of-schema-partition"></a>Comprobar la replicación de la partición del esquema
 
Para comprobar que la extensión de esquema se haya replicado correctamente en el bosque de Servicios de dominio de Active Directory, haga lo siguiente:
  
1. Inicie sesión en un controlador de dominio (que no sea el controlador de dominio que contiene el rol de maestro de esquema) en el bosque de Servicios de dominio de Active Directory, donde las extensiones de esquema se aplicaron como miembro del grupo Administradores de organización.
    
2. Abra el Editor ADSI: haga clic en **Inicio**, en **Herramientas administrativas** y en **Editor ADSI**.
    
    > [!TIP]
    > Si lo desea, haga clic en **Inicio**; a continuación, haga clic en **Ejecutar** y escriba **adsiedit.msc** para iniciar el Editor ADSI.
  
3. En el árbol de la consola MMC, haga clic en Editor ADSI si aún no está seleccionado.
    
4. En el menú **Acción**, haga clic en **Conectar con**.
    
5. En el cuadro de diálogo **Configuración de conexión**, en **Seleccione un contexto de nomenclatura conocido**, seleccione **Esquema** y haga clic en **Aceptar**.
    
6. En el contenedor de esquema, busque CN=ms-RTC-SIP-SchemaVersion. Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema se ha actualizado y replicado correctamente. Si este objeto no existe o el valor de los atributos **rangeUpper** y **rangeLower** es distinto de lo que se ha especificado, el esquema no se ha modificado o no se ha replicado.
    
> [!NOTE]
> Si la comprobación de la replicación del esquema aún no muestra una replicación correcta, espere aproximadamente 15 minutos y vuelva a comprobarlo. La replicación de Active Directory se basa en un modelo de coherencia flexible y puede producirse cierta latencia de replicación, en función de una serie de factores en el servidor y la infraestructura. 
  

