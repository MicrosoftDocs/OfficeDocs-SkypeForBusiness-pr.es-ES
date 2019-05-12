---
title: Combinar información heredada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: El FQDN externo de conferencia Web permite a los usuarios externos participar en las reuniones locales. Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencia web del servidor perimetral heredado.
ms.openlocfilehash: 3e426af0b08660eaef619d4fd9cec9da2ca11b32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919755"
---
# <a name="legacy-merge"></a>Combinar información heredada

El **FQDN externo de conferencia Web** permite a los usuarios externos participar en las reuniones locales. Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencia web del servidor perimetral heredado.

El valor de **puerto externo de conferencia Web externo** de **443** es el puerto de protocolo de inicio de sesión (SIP) de protocolo de Control de transmisión (TCP) predeterminado configurado para los clientes de conferencia. Si no se utilizó el valor predeterminado, actualice el valor del **puerto externo de conferencias Web externas** .

Active la casilla de verificación **grupo de servidores perimetrales esta se usa para la federación y la conectividad de mensajería instantánea pública** si piensa usar este servidor perimetral para la federación. Si tiene varios servidores perimetrales implementados, sólo uno de ellos se habilitará para la federación. Si no se activa esta casilla y más adelante decide que desea habilitar la federación, debe volver a ejecutar al Asistente para la combinación de generador de topología, así como publicar la topología. Para obtener información detallada, vea [fase 4: combinar topologías](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).


