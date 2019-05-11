---
title: Expansor de configuración SBA de registrador
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Editar la configuración de resistencia y configure las siguientes propiedades:'
ms.openlocfilehash: caac7c2e8b4f5e08ef4051f092f7a02d6762c308
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910280"
---
# <a name="registrar-sba-settings-expander"></a>Expansor de configuración SBA de registrador

Editar la configuración de **resistencia** y configure las siguientes propiedades:

- Seleccione **servicio de usuario asociado y grupo de registrador de copia de seguridad** de la lista.

    De forma opcional, active la casilla de verificación **conmutación automática por error y conmutación por recuperación de Voice** .

    Configurar el **intervalo de detección de error de voz (s)** y el **intervalo de la conmutación por recuperación de Voice (seg.)**. De forma predeterminada, los intervalos son 120 para la detección de error de voz y 240 segundos para la conmutación por recuperación de Voice.

    > [!CAUTION]
    > El número de segundos que se definen para los intervalos de conmutación por error y conmutación por recuperación se debería probar detenidamente para asegurarse de que la resistencia funciona según lo previsto. Si se establece el intervalo en baja (es decir, menos de 120 segundos) o la conmutación por error y la conmutación por recuperación establecer demasiado estrechamente pueden ocasionar que la conmutación por error real y la conmutación por recuperación no funciona según lo previsto.

  **Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.

  **Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.

  **Ayuda.** Abre esta pantalla de ayuda.

## <a name="see-also"></a>Vea también

[Planeación de resistencia de Enterprise Voice](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
