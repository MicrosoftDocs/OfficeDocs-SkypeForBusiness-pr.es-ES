---
title: Expansor de configuración SBA de registrador
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Modifique la configuración de la Resistencia y configure las siguientes propiedades:'
---

# <a name="registrar-sba-settings-expander"></a>Expansor de configuración SBA de registrador

Modifique la configuración de la **Resistencia** y configure las siguientes propiedades:

- Seleccione **Servicio de usuario asociado y grupo de registrador de reserva** en la lista.

    Opcionalmente, puede activar la casilla **Conmutación por error y conmutación por recuperación automática para voz**.

    Configure el **Intervalo de detección de errores de voz (s)** y el **Intervalo de conmutación por recuperación de voz (s)**. De forma predeterminada, los intervalos son de 120 segundos para la detección de errores de voz y de 240 segundos para la conmutación por recuperación de voz.

    > [!CAUTION]
    > El número de segundos que se definen para los intervalos de conmutación por error y de conmutación por recuperación deben probarse detenidamente para garantizar que la resistencia funciona según lo previsto. Si se define el intervalo como bajo (es decir, inferior a 120 segundos) o la conmutación por error y la conmutación por recuperación se definen demasiado próximas, puede resultar en que la conmutación por error y la conmutación por recuperación reales no funcionen correctamente.

  **Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.

  **Cancelar** Descarta los cambios y cierra el cuadro de diálogo.

  **Ayuda** Muestra la ayuda de esta pantalla.

## <a name="see-also"></a>Vea también

[Planeación de la resistencia de Enterprise Voice](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)