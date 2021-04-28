---
title: Planear el Sistema telefónico con una conectividad RTC local en Skype Empresarial Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Obtenga información sobre las consideraciones de planeación de Phone System (PBX en la nube) con conectividad RTC local.
ms.openlocfilehash: afa97a00b474017e6aed5e92802e7ba13483f7af
ms.sourcegitcommit: 03ff569a0b7a8e04d7b0ab32f370a9a537fa7fe7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "52064706"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planear el Sistema telefónico con una conectividad RTC local en Skype Empresarial Server

> [!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021 después de lo cual el servicio ya no será accesible.  Además, la conectividad RTC entre el entorno local ya no se admite a través de Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.  Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](/MicrosoftTeams/direct-routing-landing-page)

Obtenga información sobre las consideraciones de planeación de Phone System (PBX en la nube) con conectividad RTC local.

Este contenido es relevante si ya tiene Skype Empresarial Server o Lync Server 2013 implementado localmente. Para otros escenarios, vea [Soluciones de telefonía de Microsoft](/microsoftteams/cloud-voice-landing-page).

 El sistema telefónico con conectividad RTC local permite aprovechar las capacidades del sistema telefónico (PBX en la nube) para los usuarios. Esto puede ayudar con los siguientes escenarios:

- Tiene algunos de los usuarios de Skype Empresarial en el entorno local y otros en Skype Empresarial Online. Ahora puede habilitar las funcionalidades y características del sistema telefónico para los usuarios que se hospedaron en Skype Empresarial Online, pero seguir usando la conectividad RTC local.

- Tiene una implementación local y desea mover algunos o todos los usuarios a Skype Empresarial Online, pero seguir usando la conectividad RTC local.

    > [!IMPORTANT]
    > Para habilitar correctamente a los usuarios para el sistema telefónico con conectividad RTC local, su dirección SIP debe estar en su propio dominio. El uso del dominio predeterminado para Microsoft 365 u Office 365, onmicrosoft.com, no se admite. 

Para obtener más información acerca del sistema telefónico, incluidas las licencias y los planes, vea Planes de llamadas [RTC para Skype Empresarial](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Comparación de características

La PBX en la nube con conectividad RTC local no ofrece el mismo conjunto de características que una solución de Telefonía IP empresarial local. Para ayudarle a decidir si la PBX en la nube con conectividad RTC local proporcionará el conjunto de características adecuado para su organización, vea Esto es lo que obtiene con PBX en la [nube.](/microsoftteams/here-s-what-you-get-with-phone-system?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2ftoc.json)

## <a name="benefits-and-planning-considerations"></a>Ventajas y consideraciones de planeación

> [!CAUTION]
> Los dispositivos Lync Phone Edition DEBEN actualizarse al firmware mínimo necesario en el entorno local ANTES de pasar a Skype Empresarial Online.
Si mueve a los usuarios de local a online antes de actualizar el firmware, los usuarios no podrán conectarse con sus teléfonos. Para corregir este problema, los usuarios deben volver al entorno local para que sus teléfonos se actualicen al firmware mínimo. NO INTENTE ACTUALIZAR AL FIRMWARE MÍNIMO NI RESTABLECER EL TELÉFONO DE FORMA AUTOMÁTICA ANTES DE VOLVER A MOVER AL USUARIO AL ENTORNO LOCAL.
Si se realiza un restablecimiento duro mientras el dispositivo no está en el firmware mínimo, se usa de forma predeterminada la autenticación de PIN, que no se admite en Skype Empresarial Online. Para obtener más información, consulte [Getting phones for Skype for Business Online](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

Al implementar el sistema telefónico con conectividad RTC local, puede mover a los usuarios a la nube a través de Skype Empresarial Online a su propio ritmo, al tiempo que conserva su conectividad RTC local. Si tiene una PBX, la seguirá usando para proporcionar conectividad RTC a los usuarios que se mueven a la nube. Una vez que un usuario se mueve a Skype Empresarial Online y sistema telefónico, su teléfono PBX heredado ya no funcionará, pero su número de teléfono se enruta a cualquiera de los clientes de Skype Empresarial para equipos o teléfonos inteligentes, así como teléfonos de escritorio compatibles con Skype Empresarial. Una vez portados, los usuarios del sistema telefónico y los usuarios de PBX heredados pueden llamarse entre sí normalmente, así como realizar y recibir llamadas RTC con su número de teléfono normal.

Es posible que tenga una característica personalizada o un complemento principal en su PBX heredada, como un centro de llamadas. Si la característica personalizada no está disponible actualmente en El sistema telefónico, debe dejar a los usuarios que requieran esa característica personalizada local con la PBX heredada y simplemente porte a los usuarios que no necesitan tener acceso a la característica personalizada al sistema telefónico con conectividad RTC local.

Para obtener una lista de PBX heredadas que interoperan directamente con Skype Empresarial Server 2015, vea  [Infrastructure Qualified for Microsoft Lync](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md). Si su PBX no está en esta lista, puede usar un controlador de borde de sesión para conectar su PBX con el sistema telefónico en Skype Empresarial Online.

### <a name="network-considerations-for-quality-and-performance"></a>Consideraciones de red para la calidad y el rendimiento

Al implementar un servicio hospedado en la nube como Sistema telefónico con conectividad RTC local, debe tener en cuenta lo siguiente. En una implementación de Skype Empresarial Server 2015 Telefonía IP empresarial local, toda la infraestructura y los clientes se encuentran en la propia red de la empresa. La calidad y el rendimiento de esta red, que es fundamental para audio y vídeo de alta calidad, están bajo el control directo del personal de la empresa. Con el sistema telefónico con conectividad RTC local, hay tres redes implicadas, dos de las cuales el cliente es responsable, pero solo una de las cuales el personal de la empresa tiene control directo sobre:

- **Red global de entrega de medios de Microsoft** Infraestructura y red en la nube global de Microsoft. Los servidores del sistema telefónico y el tráfico atraviesan esta red.

- **Interconexión RTC empresarial/en la nube** Esta es la red que conecta la empresa a la nube. Esto no es necesariamente lo mismo que la conexión genérica a Internet.

- **Red propia de su empresa** La calidad de los medios en tiempo real depende en gran medida de su propia red: especialmente la red WiFi y la calidad de la interconexión usada para llegar a la nube.

> [!NOTE]
> Para obtener más información sobre cómo ajustar el rendimiento en Skype Empresarial Online, vea [Tune Skype for Business Online performance](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>Requisitos previos para usar el sistema telefónico con conectividad RTC local

Para poder configurar el sistema telefónico con conectividad RTC local y mover usuarios a Skype Empresarial Online, debe confirmar que tiene los siguientes requisitos previos:

 **Versiones de servidor locales.** Las versiones de los servidores de la implementación local deben aparecer en la siguiente tabla para admitir sistema telefónico con conectividad RTC local.


| **Rol del servidor**                                       | **Versiones compatibles\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Perímetro de federación\*\*  <br/>                            | Skype Empresarial Server 2015  <br/>                                                                              |
| Servidor de grupo interno de la ruta de federación de próximo salto  <br/> | Skype Empresarial Server 2015, marzo de 2016 Actualización acumulativa 6.0.9319.235 o posterior (front-end o director)  <br/> |
| Servidor de usuario front-end  <br/>                          | Skype Empresarial Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Servidor perimetral  <br/>                                    | Skype Empresarial Server 2015  <br/>                                                                              |
| Servidor de mediación  <br/>                               | Skype Empresarial Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Las versiones mínimas admitidas son:

- Skype Empresarial Server 2015, marzo de 2016 Actualización acumulativa 6.0.9319.235

- Lync Server 2013 Julio de 2015 Actualización acumulativa 5.0.8308.920

\*\*La ruta de federación para todos los dominios SIP admitidos debe enrutar a través del servidor perimetral de Skype Empresarial Server 2015 que ejecute la actualización acumulativa de marzo de 2016 o posterior. Si el grupo de usuarios está en Lync Server 2013, ese tráfico de grupo de servidores externo permanece en Lync Server 2013 Edge Server. 

Además, debe asegurarse de lo siguiente:

- **El Telefonía IP empresarial local se configura y prueba para los** usuarios locales Esto incluye componentes de conectividad RTC. Para obtener más información, vea los siguientes temas si usa Skype Empresarial Server 2015, vea [Plan for Telefonía IP empresarial in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) e Deploy Telefonía IP empresarial in Skype for Business Server [2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Si usa Lync Server 2013, vea [Planning for Telefonía IP empresarial in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice) and [Deploying Telefonía IP empresarial in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-enterprise-voice).

- **Sincronización de Active Directory** Debe configurar la sincronización de Active Directory con Azure AD Connect. Para obtener más información, vea [Managing Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > La versión de AAD Connect que use debe ser la versión 1.0.9125.0 o posterior. Si usa una versión anterior de las herramientas de AAD Connect o DirSync, actualice a la versión compatible. Puede actualizar la instalación actual y mantener las reglas personalizadas que haya definido en su entorno. 

- **Configurar la implementación híbrida** Independientemente de si todos los usuarios de Skype Empresarial están actualmente en línea o localmente, o si actualmente tiene una combinación, debe completar los pasos para configurar una implementación híbrida de Skype Empresarial Server o Lync Server 2013, tal como se describe en [Deploy hybrid connectivity between Skype for Business Server and Office 365](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json). Para obtener más información sobre implementaciones híbridas, vea [Plan hybrid connectivity between Skype for Business Server and Office 365](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json). 

    Si usa Lync Server 2013, vea [Lync Server 2013 hybrid](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-2013-hybrid).

- **(Recomendado) Servicios de federación de Active Directory (AD FS).** Se recomienda implementar AD FS para admitir el inicio de sesión único. Para obtener más información, vea Servicios de federación [de Active Directory (AD FS).](/previous-versions/windows/it-pro/windows-server-2003/cc736690(v=ws.10))

Para obtener información acerca de la implementación del sistema telefónico, vea [Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server](enable-users-for-phone-system.md).