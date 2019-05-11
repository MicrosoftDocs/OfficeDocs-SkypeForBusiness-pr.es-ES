---
title: Tabla de cuadros de diálogo en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: En la tabla de cuadros de diálogo es una tabla de apoyo que almacena la información sobre DialogIDs para sesiones de punto a punto.
ms.openlocfilehash: 379956a2c77c60a53e702913d81b25b41dc2fc23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901132"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Tabla de cuadros de diálogo en Skype para Business Server 2015
 
En la tabla de cuadros de diálogo es una tabla de apoyo que almacena la información sobre DialogIDs para sesiones de punto a punto.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Tiempo de solicitud de sesión; se utiliza en forma conjunta con SessionIDSeq para identificar de forma exclusiva una sesión.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con SessionIDTime para identificar de forma exclusiva una sesión.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Suma de comprobación de la ExternalID. Este campo se usa para aumentar la velocidad de las búsquedas de la base de datos.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |En el identificador de diálogo SIP, que se almacena como un archivo binario. El formato del binario es:  <br/> cuadro de diálogo; de etiqueta; para etiqueta  <br/> Estos datos pueden convertirse a formato de texto con esta sintaxis:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

