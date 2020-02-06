---
title: Comprobar la replicación de la partición del esquema
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Para comprobar que la extensión de esquema se ha replicado correctamente en el bosque de los servicios de dominio de Active Directory, haga lo siguiente:'
ms.openlocfilehash: f2e8c181f01e841ebc6b251d8215a8d448db0b04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823274"
---
# <a name="verify-replication-of-schema-partition"></a>Comprobar la replicación de la partición del esquema
 
Para comprobar que la extensión de esquema se ha replicado correctamente en el bosque de los servicios de dominio de Active Directory, haga lo siguiente:
  
1. Inicie sesión en un controlador de dominio (que no sea el controlador de dominio que desempeña la función de maestro de esquema) en el bosque de los servicios de dominio de Active Directory, donde las extensiones de esquema se han aplicado como miembro del grupo administradores de empresa.
    
2. Abra ADSI Edit: haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **ADSI Edit**.
    
    > [!TIP]
    > Como alternativa, haga clic en **Inicio**y, a continuación, en **Ejecutar**, escriba **ADSIEdit. msc** para iniciar ADSI Edit.
  
3. En el árbol de Microsoft Management Console (MMC), si aún no está seleccionado, haga clic en ADSI Edit.
    
4. En el menú **Acción**, haga clic en **Conectar con**.
    
5. En el cuadro de diálogo **Configuración de conexión**, en **Seleccione un contexto de nomenclatura conocido**, seleccione **Esquema** y, luego, haga clic en **Aceptar**.
    
6. En el contenedor de esquema, busque CN=ms-RTC-SIP-SchemaVersion. Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema se ha actualizado y replicado correctamente. Si este objeto no existe o si los valores de los atributos **rangeUpper** y **rangeLower** no son los especificados, el esquema no se modificó o no se ha replicado.
    
> [!NOTE]
> Si la comprobación de la replicación del esquema aún no muestra una replicación correcta, espere aproximadamente 15 minutos y, a continuación, vuelva a comprobarlo. La replicación de Active Directory se basa en un modelo de coherencia separada y puede producirse cierta latencia de replicación, en función de una serie de factores en el servidor y en la infraestructura. 
  

