---
title: Comprobar la replicación de la partición de esquema
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Para comprobar que se han replicado correctamente la extensión del esquema en el bosque de servicios de dominio de Active Directory, haga lo siguiente:'
ms.openlocfilehash: a5628e369ffc796affe9984cef8ecb1ba044ec8a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-of-schema-partition"></a>Comprobar la replicación de la partición de esquema
 
Para comprobar que se han replicado correctamente la extensión del esquema en el bosque de servicios de dominio de Active Directory, haga lo siguiente:
  
1. Inicie sesión en un controlador de dominio (que no sea controlador de dominio que desempeña la función de maestro de esquema) en el bosque de servicios de dominio de Active Directory, donde se aplicaron las extensiones de esquema como miembro del grupo Administradores de organización.
    
2. Abrir Editar ADSI: Haga clic en **Inicio**, haga clic en **Herramientas administrativas**y, a continuación, haga clic en **Edición de ADSI**.
    
    > [!TIP]
    > O bien, haga clic en **Inicio**, haga clic en **Ejecutar**, escriba **adsiedit.msc** para iniciar ADSI Edit.
  
3. En el árbol de la consola de Microsoft Management Console (MMC), si no está ya seleccionada, haga clic en edición de ADSI.
    
4. En el menú **Acción**, haga clic en **Conectar con**.
    
5. En el cuadro de diálogo **Configuración de conexión**, en **Seleccione un contexto de nomenclatura conocido**, seleccione **Esquema** y, luego, haga clic en **Aceptar**.
    
6. Bajo el contenedor del esquema, busque CN = ms-RTC-SIP-SchemaVersion. Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema correctamente se actualiza y replica. Si este objeto no existe o si los valores de los atributos **rangeUpper** y **rangeLower** no se especifica, a continuación, el esquema no se modificó o no se ha replicado.
    
> [!NOTE]
> Si la verificación de la replicación del esquema no muestra todavía una replicación correcta, espere aproximadamente 15 minutos y compruébelo de nuevo. Replicación de Active Directory se basa en un modelo de coherencia no estricta y cierta latencia de replicación puede producirse, basándose en una serie de factores en el servidor y la infraestructura. 
  

