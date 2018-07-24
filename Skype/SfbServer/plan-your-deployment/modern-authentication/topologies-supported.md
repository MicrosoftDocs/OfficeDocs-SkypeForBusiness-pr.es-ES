---
title: Topologías de Skype Empresarial compatibles con la autenticación moderna
ms.author: tracyp
author: MSFTTracyP
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: En este artículo se indican las topologías en línea y locales que son compatibles con la autenticación moderna de Skype Empresarial, así como las características de seguridad que se aplican a cada topología.
ms.openlocfilehash: cc849dc1df0f4bf97bb362449ef1ded58596cb91
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001802"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Topologías de Skype Empresarial compatibles con la autenticación moderna
 
En este artículo se indican las topologías en línea y locales que son compatibles con la autenticación moderna de Skype Empresarial, así como las características de seguridad que se aplican a cada topología.
  
## <a name="modern-authentication-in-skype-for-business"></a>Autenticación moderna en Skype Empresarial

Skype Empresarial puede aprovechar las ventajas en seguridad que proporciona la autenticación moderna. Como Skype Empresarial colabora estrechamente con Exchange, el comportamiento de inicio de sesión que verán los usuarios de los clientes de Skype Empresarial también reflejará el estado de MA de Exchange. Lo mismo sucederá si tiene un híbrido de dominio dividido de Skype Empresarial. Esto supone una gran cantidad de piezas que se pueden cambiar, pero el objetivo es crear una lista de las topologías compatibles que sea muy fácil de visualizar.
  
Para Skype Empresarial, Skype Empresarial Online, Exchange Server y Exchange Online, ¿qué topologías serán compatibles con MA?
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a>Topologías compatibles con MA en Skype Empresarial

Hay potencialmente dos aplicaciones de servidor y dos cargas de trabajo de Office 365 que emplean las topologías de Skype Empresarial utilizadas por MA.
  
- Skype para profesionales (CU 5) del servidor local
    
- Skype Empresarial Online (SFBO)
    
- Exchange Server local
    
- Exchange Server Online (EXO)
    
Otra parte importante de MA es saber dónde tendrá lugar la autenticación (authN) y la autorización (authZ) de los usuarios. Las dos opciones son:
  
- Azure AD, en línea en la nube de Microsoft
    
- Servidor de federación de Active Directory (ADFS) local
    
Por lo que tiene un aspecto similar, con EXO y SFBO en la nube con Azure AD y Exchange Server (EXCH) y Skype para profesionales el servidor (SFB) prem.
  
![Un ejemplo de todas las aplicaciones (Exchange y Skype Empresarial) y las cargas de trabajo (EXO y SFBO), así como de los servidores de autorización (ADFS y evoSTS) que puedan estar involucrados cuando se activa MA.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
Estas son las topologías compatibles. Tenga en cuenta estos puntos clave para interpretar los gráficos:
  
- Si el icono aparece atenuado o en color gris, no se usa en el escenario.
    
- EXO es Exchange Online.
    
- SFBO es Skype Empresarial Online.
    
- EXCH es Exchange local.
    
- SFB es Skype Empresarial local.
    
- Los triángulos representan los servidores de autorización, de manera que, por ejemplo, Azure AD es un triángulo con una nube detrás.
    
- Las flechas apuntan al servidor de autorización que se utilizará cuando los clientes intenten llegar al recurso de servidor especificado.
    
En primer lugar, vamos a cubrir MA con Skype Empresarial en las topologías de solo local o solo nube.
  
> [!IMPORTANT]
> ¿Está listo para configurar la autenticación moderno en Skype para profesionales en línea? Los pasos para habilitar esta característica son derecho [aquí](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). 
  
|Nombre de topología  <br/> |Ejemplo  <br/> |Descripción  <br/> |Compatible  <br/> |
|:-----|:-----|:-----|:-----|
|Solo nube  <br/> |![SFB compatible con topología de MA, solo nube.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Usuarios hospedados/buzones ubicados: en línea   <br/> |MA está activado tanto para EXO como para SFBO.  <br/> Por lo tanto, el servidor de autorización es Azure AD.  <br/> |Autenticación multifactor (MFA), la autenticación (CBA), acceso condicional (CA) basada en certificados de cliente y administración de aplicaciones móviles (MAM) con Intune. \*  <br/> |
|Solo local  <br/> |![SFB compatible con topología de MA, solo local.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Usuarios hospedados/buzones ubicados: en local  <br/> |MA está activado para SFB local.  <br/> Por lo tanto, el servidor de autorización es ADFS.  <br/> Para obtener información detallada de la configuración, vea [en este artículo.](https://technet.microsoft.com/en-us/library/mt710548.aspx) <br/> |MFA (escritorio de Windows solo: los clientes móviles no son compatibles). No hay ninguna característica de integración de Exchange.  <br/> |
   
> [!IMPORTANT]
> Se recomienda que el estado de MA sea el mismo en Skype Empresarial y Exchange (y sus homólogos en línea) para reducir el número de mensajes. 
  
Las topologías mixtas implican combinaciones de híbridos de dominio dividido de SFB. Estas son las topologías mixtas que son compatibles en este momento:
  
|Nombre de topología  <br/> |Ejemplo  <br/> |Descripción  <br/> |Compatible  <br/> |
|:-----|:-----|:-----|:-----|
|Mixta 1  <br/> |![SFB compatible con topología de MA, Mixto 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Usuarios hospedados/buzones ubicados: EXO y SFB  <br/> |MA no está habilitado para SFB; no hay ninguna característica de MA para SFB disponible en esta topología.  <br/> |No hay ninguna característica de MA para SFB.  <br/> |
|Mixta 2  <br/> |![MA compatible con la topología 2 mixta de S4B, SFBO más MA trabajando con EXCH local.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Usuarios hospedados/buzones ubicados: EXCH y SFBO  <br/> |MA en sólo es para SFBO. El servidor de autorización es Azure AD para los usuarios alojados en SFBO, pero AD para EXCH local.  <br/> |MFA, CBA, entidad emisora de certificados/MAM con Intune.\*  <br/> |
|Mixta 3  <br/> |![MA compatible con SFB, EXO con MA activado, además de EXCH y SFB local.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Usuarios hospedados/buzones ubicados: EXO + SFB o EXCH + SFB  <br/> |No hay ninguna característica de MA para SFB disponible en esta topología.  <br/> |No hay ninguna característica de MA para SFB.  <br/> |
|Mixta 4  <br/> |![MA compatible con SFB, SFBO con MA activado, además de EXCH y SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Usuarios hospedados/buzones ubicados: EXCH +SFBO o EXCH + SFB   <br/> |MA está activada para SFBO, por lo tanto, el servidor de autorización es Azure AD para los usuarios alojados en SFBO. Los usuarios en prem SFB y EXO utilizar AD.  <br/> |MFA, CBA, entidad emisora de certificados/MAM con Intune en línea sólo para los usuarios.\*  <br/> |
|Mixta 5  <br/> |![MA compatible en SFB, EXO con MA y SFBO con MA, además de EXCH y SFB local.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Usuarios hospedados/buzones ubicados: EXO + SFBO, EXO + SFB, EXCH + SFBO o EXCH + SFB  <br/> |MA es en EXO y SFBO, por lo tanto, que el servidor de autorización es Azure AD para los usuarios alojados en SFBO; los usuarios en prem EXCH y SFB utilizar AD.  <br/> |MFA, CBA, entidad emisora de certificados/MAM con Intune en línea sólo para los usuarios.\*  <br/> |
|6 mixto  <br/> |![Eu una topología 6 mixta, la autenticación moderna está activada en las cuatro ubicaciones posibiles, que es la situación ideal en lo que se refiere a autenticación moderna.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Usuarios hospedados/buzones ubicados: EXO + SFBO, EXO + SFB, EXCH + SFBO o EXCH + SFB  <br/> |MA es en cualquier lugar, por lo tanto, el servidor de autorización es Azure AD para todos los usuarios. (en línea y local)  <br/>  Consulte [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) para los pasos de implementación. <br/> |MFA, CBA y entidad emisora de certificados/MAM (a través de Intune) para todos los usuarios.  <br/> |
   
\*-MFA incluye el escritorio de Windows, MAC, iOS, dispositivos Android y teléfonos de Windows; CBA incluye el escritorio de Windows, iOS y Android dispositivos; Entidad emisora de certificados/MAM con Intune, incluye dispositivos Android y iOS. 
  
> [!IMPORTANT]
> Es muy importante tener en cuenta que los usuarios pueden ver **varios mensajes** en algunos casos, sobre todo donde el estado de MA no es el mismo en todos los recursos de los servidores que los clientes pueden necesitar y solicitar, como es el caso de todas las versiones de las topologías mixtas. 

> [!IMPORTANT]
> Tenga en cuenta también que en algunos casos (mixto 1, 3 y 5 específicamente) se debe establecer una clave de registro [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) para la configuración correcta para los clientes de escritorio de Windows.
  

