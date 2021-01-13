---
title: Tabla Dialogs en Skype Empresarial Server 2015
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
description: La tabla Cuadros de diálogo es una tabla compatible que almacena la información acerca de dialogIDs para sesiones punto a punto.
ms.openlocfilehash: a4f0bb8c63e165985ef09af8f9aafa071529bf1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816050"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Tabla Dialogs en Skype Empresarial Server 2015
 
La tabla Cuadros de diálogo es una tabla compatible que almacena la información acerca de dialogIDs para sesiones punto a punto.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal  <br/> |Hora de la solicitud de sesión; se usa junto con SessionIDSeq para identificar de forma única una sesión.  <br/> |
|**SessionIdSeq** <br/> |entero  <br/> |Principal  <br/> |Número de identificador para identificar la sesión. Se usa junto con SessionIDTime para identificar de forma única una sesión.  <br/> |
|**ExternalChecksum** <br/> |entero  <br/> | <br/> |Suma de comprobación de ExternalID. Este campo se usa para aumentar la velocidad de las búsquedas en la base de datos.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |Identificador de cuadro de diálogo SIP, almacenado como binario. El formato del binario es:  <br/> dialog;from-tag;to-tag  <br/> Estos datos pueden convertirse en formato de texto con esta sintaxis:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

