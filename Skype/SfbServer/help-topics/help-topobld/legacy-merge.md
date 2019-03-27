---
title: Combinar información heredada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: El FQDN externo de conferencia Web permite a los usuarios externos participar en las reuniones locales. Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencia web del servidor perimetral heredado.
ms.openlocfilehash: a6bb1ee83496e98f6097905fdf24c62d20d657ae
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897181"
---
# <a name="legacy-merge"></a>Combinar información heredada

El **FQDN externo de conferencia Web** permite a los usuarios externos participar en las reuniones locales. Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencia web del servidor perimetral heredado.

El valor de **puerto externo de conferencia Web externo** de **443** es el puerto de protocolo de inicio de sesión (SIP) de protocolo de Control de transmisión (TCP) predeterminado configurado para los clientes de conferencia. Si no se utilizó el valor predeterminado, actualice el valor del **puerto externo de conferencias Web externas** .

Active la casilla de verificación **grupo de servidores perimetrales esta se usa para la federación y la conectividad de mensajería instantánea pública** si piensa usar este servidor perimetral para la federación. Si tiene varios servidores perimetrales implementados, sólo uno de ellos se habilitará para la federación. Si no se activa esta casilla y más adelante decide que desea habilitar la federación, debe volver a ejecutar al Asistente para la combinación de generador de topología, así como publicar la topología. Para obtener información detallada, vea [fase 4: combinar topologías](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).


