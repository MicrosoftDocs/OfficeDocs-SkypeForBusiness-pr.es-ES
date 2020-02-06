---
title: Conceptos básicos de DNS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 tiene software integrado que puede proporcionar servicios DNS, por lo que es posible que desee revisar la documentación disponible, como la guía de escenario de la Directiva DNS. Si lo prefiere, puede elegir una solución de terceros.
ms.openlocfilehash: 5438ee6ccedda6e840ca706cf285af49326a3bf4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815798"
---
# <a name="dns-basics"></a>Conceptos básicos de DNS
 
Windows Server 2016 tiene software integrado que puede proporcionar servicios DNS, por lo que es posible que desee revisar la documentación disponible, como la [Guía de escenario de la Directiva DNS](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide). Si lo prefiere, puede elegir una solución de terceros.
  
Le recomendamos que, como práctica recomendada, dedique un servidor específico en su implementación para proporcionar DNS. Puede configurarlo en uno de los servidores dedicados a una de las funciones de servidor de Skype empresarial, pero si ese servidor también forma parte de un grupo y se ha descargado por accidente, Skype empresarial no funcionaba correctamente hasta que se hayan restablecido los servicios DNS.
  
## <a name="dns-records"></a>Registros DNS

Cada asignación de un nombre a una dirección IP (y puede ser una dirección IPv4 o IPv6) se almacena en un registro DNS en el servidor DNS. El nombre se describe en el informe DNS específicamente como un FQDN (un nombre de dominio completo). Aunque *contoso.com* es un nombre de dominio válido, es una forma abreviada de * \*. contoso.com* , por lo que es ambiguo y podría hacer referencia a cualquier servidor del dominio. Un ejemplo de un FQDN que haría referencia a un único servidor de su dominio podría ser **meeting01.contoso.com**.
  
> [!IMPORTANT]
> De manera predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre de host, en lugar de un nombre de dominio completo (FQDN). El generador de topología usa FQDN, no nombres de host. Por lo tanto, debe configurar un sufijo DNS en el nombre del equipo para implementarse como servidor perimetral que no está unido a un dominio. **Use solo caracteres estándar** (incluidos a-z, a-z, 0-9 y guiones) al asignar FQDN a los servidores que ejecutan Skype empresarial Server. No utilice caracteres Unicode ni de subrayado. Los caracteres no estándar en una dirección URL o un FQDN a menudo no son compatibles con DNS externas y CA públicas (es decir, cuando el FQDN debe asignarse al SN en el certificado).
  
Además de una dirección IP, el FQDN podría asignarse a una **VIP** (una dirección IP virtual). Una VIP es una dirección IP que no se corresponde con una interfaz de red física real. Una VIP a menudo apunta a un grupo de servidores que realizan una función de servidor o a un par de servidores configurados para redundancia y tolerancia a errores.
  
Existen varios tipos de registros DNS, los que son más importantes para esta explicación: 
  
- **A** : un registro de dirección o un registro de host, devuelve una dirección IPv4 de 32 bits. Suele usarse para asignar nombres de host a una dirección IP del host.
    
- **AAAA** : un registro de dirección IPv6. Devuelve una dirección IPv6 de 128 bits. Suele usarse para asignar nombres de host a una dirección IP del host.
    
- **CNAME** : un registro de nombre canónico. Se resuelve un nombre en otro: la búsqueda DNS volverá a intentar la búsqueda con el nombre nuevo.
    
- **SRV** : un registro de servicio (registro SRV) especifica un servicio (un proceso en un servidor) al que se tiene acceso en una combinación de puerto y IP específica. Los nombres de los servicios que requieren un registro de servicio son fijos y no se pueden personalizar para que formen parte de su dominio SIP. Algunos servicios de usuario usan direcciones URL simples. Un registro SRV debe apuntar a una ubicación en el mismo dominio SIP, por lo que si tiene varios dominios necesitará varios registros SRV para un servicio determinado.
    
## <a name="how-to-choose-a-sip-domain-name"></a>Cómo elegir un nombre de dominio SIP
<a name="BK_NameSIP"> </a>

El nombre de dominio SIP de una organización generalmente se alinea con las direcciones de correo electrónico que se proporcionan a los usuarios. Si un usuario de su organización tiene una dirección de correo electrónico como Brown@contoso.com, el \<dominio\> SIP preferido de una organización con el nombre de dominio contoso.com es simplemente contoso.com.
  
### <a name="multiple-sip-domains"></a>Varios dominios SIP

 Es posible que su organización, en algunos casos, necesite varios dominios SIP. Como ejemplo, si Fabrikam.com fue adquirido por contoso.com, es posible que necesite crear un nuevo dominio SIP que Skype empresarial Server reconoce y acepta la conexión de. Cuando lo haga, tendrá que crear un conjunto adicional de todos los registros DNS que usan contoso.com, con nuevos FQDN que muestran dónde enviar solicitudes para fabrikam.
  
## <a name="dns-load-balancing"></a>Equilibrio de carga de DNS
<a name="BK_NameSIP"> </a>

Puede usar DNS para compartir la carga de tráfico entre varios servidores que están configurados como un grupo de servidores. Para ello, debe crear varios registros A para el FQDN del grupo, cada uno de los cuales señala a la dirección IP de un nodo del grupo.
  
Consulte [equilibrio de carga de DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) para obtener más discusiones sobre el equilibrio de carga.
  

