---
title: Expansor de configuración SBA de registrador
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
ROBOTS: NOINDEX, NOFOLLOW
description: 'Edite la configuración de resistencia y configure las siguientes propiedades:'
ms.openlocfilehash: 7eb90efde862b6326ea6f43f27937751ebff0ce9
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797251"
---
# <a name="registrar-sba-settings-expander"></a>Expansor de configuración SBA de registrador

Edite la configuración de **resistencia** y configure las siguientes propiedades:

- Seleccione **servicio de usuario asociado y grupo de registro** de la copia de seguridad en la lista.

    De manera opcional, active la casilla **conmutación automática por error para voz** .

    Configure el **intervalo de detección de errores de voz (s)** y el intervalo de conmutación por recuperación de **voz (s)**. De forma predeterminada, los intervalos son de 120 segundos para la detección de errores de voz y de 240 segundos para la conmutación por voz.

    > [!CAUTION]
    > El número de segundos que defina para los intervalos de conmutación por error y failback debe probarse detenidamente para asegurarse de que la resistencia funciona de la manera esperada. Configurar el intervalo en Low (es decir, menos de 120 segundos) o el conjunto de conmutación por error y conmutación por recuperación demasiado estrecho puede dar lugar a que la conmutación por error y la conmutación de conmutación reales no funcionen de la manera esperada.

  **Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.

  **Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.

  **Ayuda.** Abre esta pantalla de ayuda.

## <a name="see-also"></a>Vea también

[Planificación de resistencia de telefonía IP empresarial](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
