---
title: Agregar colocaciones de servidor front-end 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: En una implementación de Enterprise Edition, puede combinar el servicio de conferencia A/V, el servidor de mediación o ambos en el grupo de servidores front-end. También puede implementar cada uno como servidor independiente. En la implementación de un servidor Standard Edition, el servicio de conferencia A/V siempre se combina si Conferencia está habilitada.
ms.openlocfilehash: 4abf3d4a762ed14d95b7e9f1a4964b50c77a2884
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744251"
---
# <a name="add-front-end-server-collocations-2010"></a>Agregar colocaciones de servidor front-end 2010

En una implementación de Enterprise Edition, puede combinar el servicio de conferencia A/V, el servidor de mediación o ambos en el grupo de servidores front-end. También puede implementar cada uno como servidor independiente. En la implementación de un servidor Standard Edition, el servicio de conferencia A/V siempre se combina si Conferencia está habilitada.

> [!NOTE]
> Se necesita un servicio de conferencia A/V si **Conferencia** se ha seleccionado en la página **Seleccione las características**. Un grupo de servidores front-end de Enterprise Edition puede usar un servicio de conferencia A/V o un grupo de servidores de conferencia A/V independiente. Si no se ha seleccionado Conferencia, no estará disponible el servicio para combinar el servicio de conferencia A/V.

La función de servidor de mediación puede combinarse en un servidor front-end Standard Edition o un grupo de servidores front-end Enterprise Edition. Si implementa conexiones SIP directas para una puerta de enlace de una red telefónica conmutada (RTC) cualificada que admite omisión de medios y equilibrio de carga del sistema de nombres de dominio (DNS), no es necesario un grupo independiente de servidores de mediación. No se necesita un servidor de mediación independiente, ya que las puertas de enlace cualificadas pueden realizar el equilibrio de carga de DNS para un grupo de servidores de mediación y pueden recibir tráfico de cualquier servidor de mediación de un grupo. También se recomienda colocar el servidor de mediación en un grupo de servidores front-end cuando haya implementado IP-PBXs o conectarse al controlador de borde de sesión (SBC) de un proveedor de telefonía por Internet, siempre y cuando se cumple cualquiera de las siguientes condiciones:

- El sistema IP-PBX o SBC esté configurado para recibir tráfico de cualquier servicio de mediación del grupo de servidores y pueda enrutar el tráfico uniformemente a todos los servidores de mediación del grupo.

- El sistema IP-PBX o SBC esté configurado para recibir tráfico de cualquier servicio de mediación del grupo de servidores y pueda enrutar el tráfico uniformemente a todos los servidores de mediación del grupo.

Puede usar microsoft Lync Server 2013, herramienta de planeación para evaluar si el grupo de servidores front-end donde desea colocar el servidor de mediación puede controlar la carga. Si el entorno no cumple estos requisitos, deberá implementar un grupo de servidores de mediación independiente.

En general, no se recomienda la colocación de un servidor de conferencia A/V o un servidor de mediación si su organización tiene requisitos de alta disponibilidad y escalabilidadPara obtener información detallada sobre cómo colocar estos roles de servidor en un grupo de servidores front-end en una implementación de Enterprise Edition, vea [Definir](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) y configurar un grupo de servidores front-end en la documentación sobre implementación. Para obtener más información sobre las características y los componentes de conferencia A/V, consulte [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) en la documentación sobre planeación. Para obtener más información Telefonía IP empresarial características y componentes, incluido el servidor de mediación, vea [Plan for Telefonía IP empresarial in Skype Empresarial Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) en la documentación sobre planeación.