---
title: Agregar colocación de servidor front-end
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
ROBOTS: NOINDEX, NOFOLLOW
description: En una implementación de Enterprise Edition, el servicio de conferencia A/V se combina en el grupo de servidores front-end. También puede combinar el servidor de mediación en el grupo de servidores front-end o puede implementarlo como servidor independiente. El servicio de conferencia A/V siempre se combina si la conferencia está habilitada.
ms.openlocfilehash: 093afe3a741f197b76654d4399b68bfa523d84a6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758732"
---
# <a name="add-front-end-server-collocations"></a>Agregar colocación de servidor front-end

En una implementación de Enterprise Edition, el servicio de conferencia A/V se combina en el grupo de servidores front-end. También puede combinar el servidor de mediación en el grupo de servidores front-end o puede implementarlo como servidor independiente. El servicio de conferencia A/V siempre se combina si la conferencia está habilitada.

> [!NOTE]
> Se necesita un servicio de conferencia A/V si **Conferencia** se ha seleccionado en la página **Seleccione las características**. Un grupo de servidores front-end de Enterprise Edition usa un servicio de conferencia A/V combinado. Si no se ha seleccionado Conferencia, no estará disponible el servicio para combinar de servicio de conferencia A/V.

La función de servidor de mediación puede combinarse en un servidor front-end Standard Edition o un grupo de servidores front-end Enterprise Edition. Si implementa conexiones SIP directas para una puerta de enlace de una red telefónica conmutada (RTC) cualificada que admite omisión de medios y equilibrio de carga del sistema de nombres de dominio (DNS), no es necesario un grupo independiente de servidores de mediación. No se necesita un servidor de mediación independiente, ya que las puertas de enlace cualificadas pueden realizar el equilibrio de carga de DNS para un grupo de servidores de mediación y pueden recibir tráfico de cualquier servidor de mediación de un grupo. También se recomienda colocar el servidor de mediación en un grupo de servidores front-end cuando haya implementado IP-PBXs o conectarse al controlador de borde de sesión (SBC) de un proveedor de telefonía por Internet, siempre y cuando se cumple cualquiera de las siguientes condiciones:

- El sistema IP-PBX o SBC esté configurado para recibir tráfico de cualquier servicio de mediación del grupo de servidores y pueda enrutar el tráfico uniformemente a todos los servidores de mediación del grupo.

- El sistema IP-PBX o SBC esté configurado para recibir tráfico de cualquier servicio de mediación del grupo de servidores y pueda enrutar el tráfico uniformemente a todos los servidores de mediación del grupo.

Puede usar la Herramienta de planeación para evaluar si el grupo de servidores front-end donde desea colocar el servidor de mediación puede controlar la carga. Si su entorno no cumple con estos requisitos, debe implementar un grupo independiente de servidores de mediación.

En general, no se recomienda combinar un servidor de mediación si la organización tiene requisitos de escalabilidad y alta disponibilidad. Para obtener más información sobre cómo combinar estos roles de servidor en un grupo de servidores front-end en una implementación Enterprise Edition, consulte [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) en la documentación sobre implementación. Para obtener más información sobre las características y los componentes de conferencia A/V, consulte [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) en la documentación sobre planeación. Para obtener más información Telefonía IP empresarial características y componentes, incluido el servidor de mediación, vea [Plan for Telefonía IP empresarial in Skype Empresarial Server](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) en la documentación sobre planeación.