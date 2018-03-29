---
title: Combinación heredado
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: El FQDN externo de conferencias Web permite a los usuarios externos puedan unirse a reuniones locales. Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencias web del servidor de borde heredada.
ms.openlocfilehash: 09bba6fa5532e85572a1272fde59dc0a1f7a9c1e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="legacy-merge"></a>Combinación heredado
 
El **FQDN externo de conferencias Web** permite a los usuarios externos puedan unirse a reuniones locales. Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencias web del servidor de borde heredada.
  
El valor de **puerto externo de conferencias Web externas** de **443** es el puerto de protocolo de inicio de sesión (SIP) de protocolo de Control de transmisión (TCP) predeterminado configurado para los clientes de conferencias. Si no se utilizó el valor predeterminado, actualizar el valor de **puerto externo de conferencias Web externas** .
  
Active la casilla de verificación **borde de este grupo se utiliza para la federación y la conectividad con IM pública** si piensa utilizar este servidor perimetral para la federación. Si tiene varios servidores Edge implementados, sólo uno de ellos se habilitará para la federación. Si no activa esta casilla y más adelante decide que desea habilitar la federación, debe ejecutar nuevamente el Asistente de combinación de generador de topología, así como publicar la topología. Para obtener más información, consulte [fase 4: topologías de mezcla](http://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).
  

