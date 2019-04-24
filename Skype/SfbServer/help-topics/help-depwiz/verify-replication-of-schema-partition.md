---
title: Comprobar la replicación de la partición del esquema
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Para comprobar que la ampliación del esquema se han replicado correctamente en su bosque de los servicios de dominio de Active Directory, haga lo siguiente:'
ms.openlocfilehash: 38d5983623c837e931274deef7581dd1567fc492
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234862"
---
# <a name="verify-replication-of-schema-partition"></a>Comprobar la replicación de la partición del esquema
 
Para comprobar que la ampliación del esquema se han replicado correctamente en su bosque de los servicios de dominio de Active Directory, haga lo siguiente:
  
1. Inicie sesión en su bosque de los servicios de dominio de Active Directory, donde se han aplicado las extensiones del esquema como un miembro del grupo Administradores de organización en un controlador de dominio (que no sea el controlador de dominio que contiene la función de maestro de esquema).
    
2. Abrir Editar ADSI: Haga clic en **Inicio**, haga clic en **Herramientas administrativas**y, a continuación, haga clic en **Edición de ADSI**.
    
    > [!TIP]
    > Como alternativa, haga clic en **Inicio**, a continuación, haga clic en **Ejecutar**, escriba **adsiedit.msc** para iniciar el Editor ADSI.
  
3. En el árbol de Microsoft Management Console (MMC), si aún no está seleccionado, haga clic en el Editor ADSI.
    
4. En el menú **Acción**, haga clic en **Conectar con**.
    
5. En el cuadro de diálogo **Configuración de conexión**, en **Seleccione un contexto de nomenclatura conocido**, seleccione **Esquema** y, luego, haga clic en **Aceptar**.
    
6. En el contenedor de esquema, busque CN=ms-RTC-SIP-SchemaVersion. Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema correctamente se ha actualizado y replicado. Si este objeto no existe o si los valores de los atributos **rangeUpper** y **rangeLower** no son como especificado, a continuación, el esquema no se ha modificado o no se ha replicado.
    
> [!NOTE]
> Si la verificación de la replicación del esquema no mostrar aún una replicación correcta, espere aproximadamente 15 minutos y, a continuación, compruebe de nuevo. Replicación de Active Directory se basa en un modelo de coherencia no estricta y puede producirse algunos latencia de replicación, en función de un número de factores que influyen en el servidor y la infraestructura. 
  

