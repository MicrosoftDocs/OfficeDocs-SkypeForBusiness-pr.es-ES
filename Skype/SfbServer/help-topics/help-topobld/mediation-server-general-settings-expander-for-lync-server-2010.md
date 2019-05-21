---
title: Expansor de configuración general del servidor de mediación para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Edite las propiedades de los servidores de mediación en este diálogo. En el lado izquierdo hay un conjunto de vínculos rápidos que le lleva a la configuración general, la configuración del próximo salto y la configuración de la puerta de enlace RTC. En cada sección se encuentran los siguientes ajustes:'
ms.openlocfilehash: ce58f0c64a458864c91bfd63f8b1d0f905d5374d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285722"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Expansor de configuración general del servidor de mediación para Lync Server 2010

Edite las propiedades de los servidores de mediación en este diálogo. En el lado izquierdo hay un conjunto de vínculos rápidos que le lleva a la configuración general, la configuración del próximo salto y la configuración de la puerta de enlace RTC. En cada sección se encuentran los siguientes ajustes:

 **General**:

- **FQDN**: usted edita el nombre de dominio completo del servidor de mediación

- **Asociaciones**: seleccione la casilla de verificación **asociar grupo perimetral (para componentes multimedia)** y seleccione un servidor perimetral o un grupo perimetral para que el servidor de mediación use como la ruta multimedia para el acceso externo.

  **Próximo salto**:

- **Selección del próximo salto**: seleccione en una lista el servidor front-end o el grupo front-end que se usará como la ruta de acceso del servidor de mediación para la comunicación con su implementación.

  **Puerta de enlace RTC**:

  **Puerta de enlace RTC del servidor**de mediación:

- **Puertos de escucha**: defina los puertos en los que escuchará el servidor de mediación. Puede definir un puerto para **TLS** o para la seguridad de la capa de transporte, **TCP**o protocolo de control de transporte. Para que la entrada de puerto para TCP esté disponible, debe activar la casilla de **Habilitar puerto TCP**.

    > [!IMPORTANT]
    > Consulte la documentación y la configuración de la puerta de enlace de la red de telefonía pública conmutada (RTC) para determinar si necesita habilitar y definir los valores de los puertos TLS, TCP o ambos. TLS es un protocolo más seguro, que usa certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace PSTN. No todas las puertas de enlace RTC admiten TLS.

- Se muestra una lista de los troncos SIP y las puertas de enlace definidas y configuradas para su implementación. Si no hay ninguna entrada presente, no hay ningún troncal o puerta de enlace SIP configurada para su implementación. Defina y configure los troncos y las puertas de enlace en **componentes** compartidos en el generador de topología.

## <a name="see-also"></a>Vea también

[Descripción general de la Troncalización SIP](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[Opciones de implementación de la puerta de enlace RTC](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
