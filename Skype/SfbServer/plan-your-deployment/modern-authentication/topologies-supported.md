---
title: Topologías de Skype Empresarial compatibles con la autenticación moderna
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: En este artículo se enumeran las topologías locales y en línea compatibles con la autenticación moderna en Skype Empresarial, así como las características de seguridad que se aplican a cada topología.
ms.openlocfilehash: b7582b6f77a3286a2b245b4b390efee7bbef62c1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810110"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Topologías de Skype Empresarial compatibles con la autenticación moderna

En este artículo se enumeran las topologías locales y en línea compatibles con la autenticación moderna en Skype Empresarial, así como las características de seguridad que se aplican a cada topología.

## <a name="modern-authentication-in-skype-for-business"></a>Autenticación moderna en Skype Empresarial

Skype Empresarial puede aprovechar las ventajas de seguridad de la autenticación moderna. Dado que Skype Empresarial funciona estrechamente con Exchange, el comportamiento de inicio de sesión que verán los usuarios del cliente de Skype Empresarial también se verá afectado por el estado de MA de Exchange. Esto también se aplicará si tiene un dominio dividido híbrido de Skype Empresarial. Eso es una gran cantidad de elementos en movimiento, pero el objetivo aquí es una lista fácil de visualizar de topologías admitidas.

Given Skype for Business, Skype for Business online, Exchange Server, and Exchange online, what topologies are supported with MA?

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>Topologías ma admitidas en Skype Empresarial

Existen potencialmente dos aplicaciones de servidor y dos cargas de trabajo de Microsoft 365 u Office 365, implicadas en las topologías de Skype Empresarial usadas por MA.

- Skype Empresarial Server (CU 5) local

- Skype Empresarial Online (SFBO)

- Servidor de Exchange local

- Exchange Server Online (EXO)

Otra parte importante de MA es saber dónde se llevará a cabo la autenticación (authN) y la autorización (authZ) de los usuarios. Las dos opciones son:

- Azure AD, en línea en la nube de Microsoft

- Servidor de federación de Active Directory (ADFS) local

Por lo tanto, tiene un aspecto un poco similar a este, con EXO y SFBO en la nube con Azure AD, y Exchange Server (EXCH) y Skype Empresarial Server (SFB) local.

![Un ejemplo de todas las aplicaciones (Exchange y Skype Empresarial) y cargas de trabajo (EXO y SFBO) y de los dos servidores de autorización (ADFS y evoSTS) que pueden estar implicados al activar MA.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

Estas son las topologías admitidas. Ten en cuenta la clave de los gráficos:

- Si el icono está atenuado o gris, no se usa en el escenario.

- EXO es Exchange Online.

- SFBO es Skype Empresarial Online.

- EXCH es Exchange local.

- SFB es Skype Empresarial local.

- La autorización de los servidores se representa mediante triángulos, por ejemplo, Azure AD es un triángulo con una nube detrás de él.

- Las flechas apuntan al servidor de autorización que se usará cuando los clientes intenten alcanzar el recurso de servidor especificado.

En primer lugar, vamos a cubrir MA con Skype Empresarial en topologías solo locales o solo en la nube.

> [!IMPORTANT]
> ¿Está listo para configurar la autenticación moderna en Skype Empresarial Online? Los pasos para habilitar esta característica están [aquí.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)

|Nombre de la topología  <br/> |Ejemplo  <br/> |Descripción  <br/> |Compatible  <br/> |
|:-----|:-----|:-----|:-----|
|Solo nube  <br/> |![SFB compatible con topología ma, solo nube.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Usuarios ubicados o buzones ubicados: En línea  <br/> |MA está en EXO y SFBO.  <br/> Por lo tanto, el servidor de autorización es Azure AD.  <br/> |Autenticación multifactor (MFA), autenticación basada en certificados de cliente (CBA), acceso condicional (CA)/Administración de aplicaciones móviles (MAM) con Intune. \*  <br/> |
|Solo de forma preinsal  <br/> |![SFB compatible con topología ma, solo local.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Usuarios ubicados/buzones ubicados: local  <br/> |MA está en SFB local.  <br/> Por lo tanto, el servidor de autorización es ADFS.  <br/> Para obtener más información sobre la configuración, consulte [este artículo.](https://technet.microsoft.com/library/mt710548.aspx) <br/> |MFA (solo escritorio de Windows: no se admiten clientes móviles). No hay características de integración de Exchange.  <br/><p> **No se recomienda este enfoque. Consulte aquí:**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |

> [!IMPORTANT]
> Se recomienda que el estado de MA sea el mismo en Skype Empresarial y Exchange (y sus equivalentes en línea) para reducir el número de mensajes.

Las topologías mixtas implican combinaciones de híbridos de dominio dividido de SFB. Estas son las topologías mixtas admitidas actualmente:

|Nombre de la topología  <br/> |Ejemplo  <br/> |Descripción  <br/> |Compatible  <br/> |
|:-----|:-----|:-----|:-----|
|Mixto 1  <br/> |![SFB compatible con topología ma, mixta 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Usuarios ubicados/buzones ubicados: EXO y SFB  <br/> |MA no está habilitado para SFB; no hay características de SFB MA disponibles en esta topología.  <br/> |No hay características de MA para SFB.  <br/> |
|Mixto 2  <br/> |![MA compatible con la topología mixta S4B 2, SFBO más MA que trabaja con EXCH de forma predefinida.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Usuarios ubicados o buzones ubicados: EXCH y SFBO  <br/> |MA solo está en SFBO. El servidor de autorización es Azure AD para los usuarios que están en SFBO, pero AD para EXCH local.  <br/> |MFA, CBA, CA/MAM con Intune.\*  <br/> |
|Mixto 3  <br/> |![MA compatible con SFB, EXO con MA en, además de EXCH y SFB local.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Usuarios ubicados/buzones ubicados: EXO + SFB o EXCH + SFB  <br/> |No hay características de SFB MA disponibles en esta topología  <br/> |No hay características de MA para SFB.  <br/> |
|Mixto 4  <br/> |![MA compatible con SFB, SFBO con MA on, además de EXCH y SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Usuarios ubicados/buzones ubicados: EXCH +SFBO o EXCH + SFB  <br/> |MA está en SFBO, por lo tanto, el servidor de autorización es Azure AD para los usuarios que están en SFBO. Los usuarios de forma interna en SFB y EXO usan AD.  <br/> |MFA, CBA, CA/MAM con Intune solo para usuarios en línea.\*  <br/> |
|Mixto 5  <br/> |![MA compatible en SFB, EXO con MA y SFBO con MA, y EXCH y SFB local.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Usuarios ubicados/buzones ubicados: EXO + SFBO, EXO + SFB, EXCH + SFBO o EXCH + SFB  <br/> |MA está en EXO y SFBO, por lo tanto, el servidor de autorización es Azure AD para los usuarios que están en SFBO; Los usuarios de exch y SFB usan AD.  <br/> |MFA, CBA, CA/MAM con Intune solo para usuarios en línea.\*  <br/> |
|Mixto 6  <br/> |![En una topología mixta 6, la autenticación moderna está activa en las cuatro ubicaciones possibiles: la ubicación ideal cuando se trata de autenticación moderna.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Usuarios ubicados/buzones ubicados: EXO + SFBO, EXO + SFB, EXCH + SFBO o EXCH + SFB  <br/> |MA está en todas partes, por lo tanto, el servidor de autorización es Azure AD para todos los usuarios. (en línea y local)  <br/>  Consulte los [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) pasos de implementación. <br/> |MFA, CBA y CA/MAM (a través de Intune) para todos los usuarios.  <br/> |

\* - MFA incluye escritorio de Windows, MAC, iOS, dispositivos Android y Windows Phone; CBA incluye dispositivos Windows Desktop, iOS y Android; CA/MAM con Intune, incluye dispositivos Android e iOS.

> [!IMPORTANT]
> Es muy importante tener en cuenta que los usuarios pueden ver varias solicitudes en algunos **casos,** especialmente cuando el estado de MA no es el mismo en todos los recursos de servidor que los clientes pueden necesitar y solicitar, como es el caso de todas las versiones de las topologías mixtas.

> [!IMPORTANT]
> Ten en cuenta también que en algunos casos (mixto 1, 3 y 5 específicamente) se debe establecer una clave del Registro [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) para una configuración adecuada para los clientes de escritorio de Windows.


