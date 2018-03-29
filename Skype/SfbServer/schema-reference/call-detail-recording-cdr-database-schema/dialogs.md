---
title: Tabla de cuadros de diálogo en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La tabla de cuadros de diálogo es una tabla de soporte que almacena la información acerca de DialogIDs para la sesiones de peer-to-peer.
ms.openlocfilehash: b2953ff2bec35575221bc0d43785eb6c0d90e2d1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Tabla de cuadros de diálogo en Skype para Business Server 2015
 
La tabla de cuadros de diálogo es una tabla de soporte que almacena la información acerca de DialogIDs para la sesiones de peer-to-peer.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Tiempo de solicitud de sesión; se utiliza junto con SessionIDSeq para identificar una sesión.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con SessionIDTime para identificar una sesión.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Suma de comprobación de la ExternalID no. Este campo se utiliza para aumentar la velocidad de las búsquedas de base de datos.  <br/> |
|**ExternalID no** <br/> |varbinary(775)  <br/> | <br/> |Identificador de diálogo SIP, almacenado como un archivo binario. El formato del binario es:  <br/> diálogo de etiqueta; para etiqueta  <br/> Estos datos se pueden convertir a formato de texto utilizando esta sintaxis:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

