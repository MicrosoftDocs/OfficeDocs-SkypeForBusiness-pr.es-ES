---
title: Topologías de Skype empresarial compatibles con la autenticación moderna
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: En este artículo se enumeran las topologías en línea y locales que se admiten con la autenticación moderna en Skype empresarial, así como las características de seguridad que se aplican a cada topología.
ms.openlocfilehash: 443980f6ecf2bdf170974bf0fdc0dd64f3657e67
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219700"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Topologías de Skype empresarial compatibles con la autenticación moderna

En este artículo se enumeran las topologías en línea y locales que se admiten con la autenticación moderna en Skype empresarial, así como las características de seguridad que se aplican a cada topología.

## <a name="modern-authentication-in-skype-for-business"></a>Autenticación moderna en Skype empresarial

Skype empresarial puede aprovechar las ventajas de seguridad de la autenticación moderna. Como Skype empresarial trabaja estrechamente con Exchange, el comportamiento de inicio de sesión que verán los usuarios del cliente de Skype empresarial también se verá afectado por el estado de MA de Exchange. Esto también se aplicará si tiene un híbrido de dominio dividido de Skype empresarial. Esto es una gran cantidad de elementos móviles, pero el objetivo aquí es una lista fácil de visualizar de las topologías admitidas.

Skype empresarial, Skype empresarial online, Exchange Server y Exchange Online, ¿qué topologías son compatibles con MA?

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>Topologías MA admitidas en Skype empresarial

Existen potencialmente dos aplicaciones de servidor y dos cargas de trabajo de Microsoft 365 u Office 365, relacionadas con las topologías de Skype empresarial que usa MA.

- Skype empresarial Server (CU 5) local

- Skype empresarial online (SFBO)

- Exchange Server local

- Exchange Server online (EXO)

Otra parte importante de MA es saber dónde se llevará a cabo la autenticación (authn) y la autorización (authZ) de los usuarios. Las dos opciones son:

- Azure AD en línea en la nube de Microsoft

- Servidor de Federación de Active Directory (ADFS) local

Por lo tanto, con EXO y SFBO en la nube con Azure AD y Exchange Server (EXCH) y Skype empresarial Server (SFB) local, tiene un aspecto similar a este.

![Un ejemplo de todas las aplicaciones (Exchange y Skype empresarial) y las cargas de trabajo (EXO y SFBO) y los servidores de autorización (ADFS y evoSTS) que se pueden usar al activar el MA.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

Estas son las topologías admitidas. Tenga en cuenta la clave de los gráficos:

- Si el icono está atenuado o gris, no se usa en el escenario.

- EXO es Exchange Online.

- SFBO es Skype empresarial online.

- EXCH es de Exchange local.

- SFB es Skype empresarial local.

- La autorización de servidores se representa mediante triángulos, por ejemplo, Azure AD es un triángulo con una nube detrás.

- Las flechas apuntan al servidor de autorización que se utilizará cuando los clientes intenten alcanzar el recurso de servidor especificado.

En primer lugar, vamos a cubrir MA con Skype empresarial en topologías solo locales o solo en la nube.

> [!IMPORTANT]
> ¿Está listo para configurar la autenticación moderna en Skype empresarial online? Los pasos para habilitar esta característica están justo [aquí](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).

|Nombre de topología  <br/> |Ejemplo  <br/> |Descripción  <br/> |Compatible  <br/> |
|:-----|:-----|:-----|:-----|
|Solo nube  <br/> |![SFB compatible con topología de MA, solo nube.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Usuarios hospedados/buzones ubicados: en línea  <br/> |MA está activado para EXO y SFBO.  <br/> Por lo tanto, el servidor de autorización es Azure AD.  <br/> |Autenticación multifactor (MFA), autenticación basada en certificados de cliente (CBA), acceso condicional (CA)/Mobile de administración de aplicaciones (MAM) con Intune. \*  <br/> |
|Solo local  <br/> |![SFB compatible con topología de MA, solo local.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Usuarios hospedados/buzones ubicados: local  <br/> |MA está activado para SFB local.  <br/> Por lo tanto, el servidor de autorización es ADFS.  <br/> Para obtener más información sobre la configuración, consulte [este artículo.](https://technet.microsoft.com/library/mt710548.aspx) <br/> |MFA (solo escritorio de Windows: no se admiten los clientes móviles). No hay características de integración de Exchange.  <br/><p> **No se recomienda este enfoque. Consulte aquí:**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |

> [!IMPORTANT]
> Se recomienda que el estado de MA sea el mismo en Skype empresarial y Exchange (y sus equivalentes en línea) para reducir el número de mensajes.

Las topologías mixtas implican combinaciones de híbridos de dominio dividido de SFB. Estas son las topologías mixtas compatibles actualmente:

|Nombre de topología  <br/> |Ejemplo  <br/> |Descripción  <br/> |Compatible  <br/> |
|:-----|:-----|:-----|:-----|
|Mezclado 1  <br/> |![SFB compatible con topología de MA, Mixed 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Usuarios hospedados/buzones ubicados: EXO y SFB  <br/> |MA no está habilitado para SFB; no hay características de MA de SFB disponibles en esta topología.  <br/> |No hay características MA para SFB.  <br/> |
|Mixto 2  <br/> |![MA compatible con S4B Mixed Topology 2, SFBO Plus MA trabajando con EXCH local.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Usuarios hospedados/buzones ubicados: EXCH y SFBO  <br/> |MA solo está activado para SFBO. El servidor de autorización es Azure AD para los usuarios hospedados en SFBO, pero AD para EXCH local.  <br/> |MFA, CBA, CA/MAM con Intune.\*  <br/> |
|Mezclado 3  <br/> |![MA compatible con SFB, EXO con MA activado, además de EXCH y SFB local.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Usuarios hospedados/buzones ubicados: EXO + SFB o EXCH + SFB  <br/> |No hay características de MA de SFB disponibles en esta topología  <br/> |No hay características MA para SFB.  <br/> |
|Mixto 4  <br/> |![MA compatible con SFB, SFBO con MA activado, además de EXCH y SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Usuarios hospedados/buzones ubicados: EXCH + SFBO o EXCH + SFB  <br/> |MA está activado para SFBO; por lo tanto, el servidor de autorización es Azure AD para los usuarios hospedados en SFBO. Los usuarios locales de SFB y EXO usan AD.  <br/> |MFA, CBA, CA/MAM con Intune solo para usuarios en línea.\*  <br/> |
|Mixto 5  <br/> |![MA compatible en SFB, EXO con MA y SFBO con MA, y EXCH y SFB en local.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Usuarios hospedados/buzones ubicados: EXO + SFBO, EXO + SFB, EXCH + SFBO o EXCH + SFB  <br/> |MA está activado en EXO y SFBO; por lo tanto, el servidor de autorización es Azure AD para los usuarios hospedados en SFBO; los usuarios locales de EXCH y SFB usan AD.  <br/> |MFA, CBA, CA/MAM con Intune solo para usuarios en línea.\*  <br/> |
|Mixto 6  <br/> |![En una topología de 6 mixta, la autenticación moderna está activada en las cuatro ubicaciones de posibiles: el que ideal cuando se trata de la autenticación moderna.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Usuarios hospedados/buzones ubicados: EXO + SFBO, EXO + SFB, EXCH + SFBO o EXCH + SFB  <br/> |MA está en todas partes; por lo tanto, el servidor de autorización es Azure AD para todos los usuarios. (en línea y local)  <br/>  Consulte [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) los pasos de implementación. <br/> |MFA, CBA y CA/MAM (mediante Intune) para todos los usuarios.  <br/> |

\*-MFA incluye el escritorio de Windows, MAC, iOS, dispositivos Android y Windows Phone; CBA incluye el escritorio de Windows, dispositivos iOS y Android; CA/MAM con Intune, incluye dispositivos Android y iOS.

> [!IMPORTANT]
> Es muy importante tener en cuenta que es posible que los usuarios vean **varios mensajes** en algunos casos, especialmente cuando el estado del mA no es el mismo en todos los recursos del servidor que los clientes pueden necesitar y solicitar, como es el caso de todas las versiones de las topologías mixtas.

> [!IMPORTANT]
> Tenga en cuenta también que, en algunos casos (mezclado 1, 3 y 5 específicamente), se debe establecer una clave de registro [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) para la configuración adecuada para los clientes de escritorio de Windows.


