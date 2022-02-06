---
title: Seleccionar reglas de conversión
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: 'Enterprise Voice requiere que todas las cadenas de marcado se normalicen al formato E.164 con el objetivo de realizar la búsqueda inversa de números (RNL). El tronco (es decir, el tronco SIP, PBX o puerta de enlace asociada) puede requerir que los números estén en un formato de marcado local. Para convertir números del formato E.164 a un formato de marcado local, si lo desea, puede definir una o más reglas de conversión para manipular el URI de solicitud antes de enrutarlo a la entidad del mismo nivel que el tronco. Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y sustituirlo por 0144.'
---

# <a name="select-translation-rules"></a>Seleccionar reglas de conversión
 
 Enterprise Voice requiere que todas las cadenas de marcado se normalicen al formato E.164 con el objetivo de realizar la búsqueda inversa de números (RNL). El tronco (es decir, el tronco SIP, PBX o puerta de enlace asociada) puede requerir que los números estén en un formato de marcado local. Para convertir números del formato E.164 a un formato de marcado local, si lo desea, puede definir una o más reglas de conversión para manipular el URI de solicitud antes de enrutarlo a la entidad del mismo nivel que el tronco. Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y sustituirlo por 0144.
  
> [!IMPORTANT]
> La capacidad de asociar una o más reglas de conversión con una configuración de tronco de Enterprise Voice sirve de alternativa para configurar reglas de conversión en la entidad del mismo nivel que el tronco. No asocie reglas de conversión a una configuración de tronco de Enterprise Voice si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto. 
  
Para usar una regla de conversión existente, haga clic en una regla de la lista y, a continuación, en **Aceptar**.
  
Para obtener información detallada sobre los diferentes procedimientos que puede realizar mediante el Panel de control de Skype Empresarial Server, vea [Manage Skype Empresarial Server 2015](../../manage/manage.md).
  

