---
title: Tabla de cuadros de diálogo en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La tabla de cuadros de diálogo es una tabla de soporte que almacena la información sobre DialogIDs para las sesiones de punto a punto.
ms.openlocfilehash: 61230cf7f72405c4c5f27ff7b159afe4e5a7842e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296325"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Tabla de cuadros de diálogo en Skype empresarial Server 2015
 
La tabla de cuadros de diálogo es una tabla de soporte que almacena la información sobre DialogIDs para las sesiones de punto a punto.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Hora de la solicitud de sesión; se usa en conjunción con SessionIDSeq para identificar de forma única una sesión.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Número de identificación para identificar la sesión. Se usa en conjunción con SessionIDTime para identificar de forma única una sesión.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Suma de comprobación de la ExternalID. Este campo se usa para aumentar la velocidad de las búsquedas en la base de datos.  <br/> |
|**ExternalId** <br/> |varbinary (775)  <br/> | <br/> |IDENTIFICADOR del cuadro de diálogo SIP, almacenado como binario. El formato del binario es:  <br/> cuadro de diálogo; desde: etiqueta; to-Tag  <br/> Estos datos se pueden convertir a formato de texto con esta sintaxis:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

