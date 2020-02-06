---
title: Combinar información heredada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: El FQDN externo de las conferencias web permite a los usuarios externos unirse a reuniones locales. Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencias web del servidor perimetral heredado.
ms.openlocfilehash: 19e508bdaaf44f64b3d907070d96a3691ce611c0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819692"
---
# <a name="legacy-merge"></a>Combinar información heredada

El **FQDN externo de las conferencias web** permite a los usuarios externos unirse a reuniones locales. Escriba el nombre de dominio completo (FQDN) de la interfaz externa de conferencias web del servidor perimetral heredado.

El valor de **Puerto externo de conferencias web externas** de **443** es el puerto de protocolo de inicio de sesión (SIP) del Protocolo de control de transmisión predeterminado (TCP) configurado para los clientes de conferencia. Si no se usó el valor predeterminado, actualice el valor del **Puerto externo de las conferencias web externas** .

Seleccione la casilla **este grupo de bordes se usa para la Federación y conectividad de mensajería instantánea pública** si tiene previsto usar este servidor perimetral para la Federación. Si tiene varios servidores perimetrales implementados, solo uno de ellos estará habilitado para la Federación. Si no activa esta casilla y decide más tarde que desea habilitar la Federación, debe volver a ejecutar el Asistente para la combinación del generador de topología, así como publicar su topología. Para obtener más información, consulte [fase 4: combinar topologías](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).


