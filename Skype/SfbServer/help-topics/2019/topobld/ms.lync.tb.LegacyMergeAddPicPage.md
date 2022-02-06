---
title: Combinar información heredada
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: 'NOINDEX, NOFOLLOW'
description: El nombre de dominio completo externo de conferencia web permite a los usuarios externos participar de reuniones locales. Especifique el nombre de dominio completo (FQDN) de la interfaz externa de la conferencia web del servidor perimetral heredado.
---

# <a name="legacy-merge"></a>Combinar información heredada

El **nombre de dominio completo externo de conferencia web** permite a los usuarios externos participar de reuniones locales. Especifique el nombre de dominio completo (FQDN) de la interfaz externa de la conferencia web del servidor perimetral heredado.

El valor de **Puerto de conferencia web externo** de **443** es el puerto TCP (protocolo de control de transmisión) de SIP (protocolo de inicio de sesión) predeterminado para clientes de conferencia. Si no se usó el valor predeterminado, actualice el valor de **Puerto de conferencia web externo**.

Active la casilla **Este grupo de servidores perimetrales se usa para federación y conectividad de mensajería instantánea pública** si tiene previsto usar este servidor perimetral para federación. Si tiene implementados varios servidores perimetrales, solo se habilitará uno de ellos para la federación. Si no marca esta casilla y más adelante decide que desea habilitar la federación, es necesario volver a ejecutar el asistente de combinación del Generador de topologías, además de publicar la topología. Para obtener información detallada, consulte [Phase 4: Merge Topologies](/previous-versions/office/lync-server-2013/phase-4-merge-topologies).