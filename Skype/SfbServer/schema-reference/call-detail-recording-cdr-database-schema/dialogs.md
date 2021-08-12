---
title: Tabla de cuadros de diálogo Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La tabla Cuadros de diálogo es una tabla de soporte que almacena la información sobre dialogIDs para sesiones punto a punto.
ms.openlocfilehash: 368abb6131367434edbdf1fe142a376fe9a155277eec8b369482545146dbdc3b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302284"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Tabla de cuadros de diálogo Skype Empresarial Server 2015
 
La tabla Cuadros de diálogo es una tabla de soporte que almacena la información sobre dialogIDs para sesiones punto a punto.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal  <br/> |Hora de la solicitud de sesión; se usa junto con SessionIDSeq para identificar de forma única una sesión.  <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Principal  <br/> |Número de identificador para identificar la sesión. Se usa junto con SessionIDTime para identificar de forma única una sesión.  <br/> |
|**ExternalChecksum** <br/> |Entero  <br/> | <br/> |Suma de comprobación del ExternalID. Este campo se usa para aumentar la velocidad de las búsquedas de bases de datos.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |Identificador de cuadro de diálogo SIP, almacenado como binario. El formato del binario es:  <br/> dialog;from-tag;to-tag  <br/> Estos datos pueden convertirse en formato de texto con esta sintaxis:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

