---
title: Conceptos básicos DNS
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 tiene software integrada que puede proporcionar servicios DNS, por lo que es posible que desee revisar la documentación disponible, como la Guía de escenario de directiva de DNS. Puede elegir una solución de terceros si lo prefiere.
ms.openlocfilehash: 297dc905a308806aec9228a9514f8e1bd65a245b
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839058"
---
# <a name="dns-basics"></a>Conceptos básicos DNS
 
Windows Server 2016 tiene software integrada que puede proporcionar servicios DNS, por lo que es posible que desee revisar la documentación disponible, como la [Guía de escenario de directiva de DNS](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide). Puede elegir una solución de terceros si lo prefiere.
  
Se recomienda como práctica recomendada de dedicar un servidor específico en su implementación para proporcionar DNS. Se podría potencialmente establecido en uno de los servidores dedicados a uno de los Skype para funciones de servidor empresarial, pero si ese servidor también formaba parte de un grupo de servidores y obtuvo de baja por accidente Skype para profesionales sería mal funcionamiento hasta que se restablezca servicios DNS.
  
## <a name="dns-records"></a>Registros DNS

Cada asignación de un nombre a una dirección IP (y que podría ser una dirección IPv4 o IPv6) se almacena en un registro DNS en el servidor DNS. El nombre se describe en el informe de DNS específicamente como un FQDN, un nombre de dominio completo. Mientras *contoso.com* es un nombre de dominio válido, es una abreviatura de * \*. contoso.com* , por lo que es ambiguo y, posiblemente, podría hacer referencia a cualquier servidor en el dominio. Un ejemplo de un FQDN que hace referencia a un único servidor en su dominio podría ser **meeting01.contoso.com**.
  
> [!IMPORTANT]
> De manera predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre de host, en lugar de un nombre de dominio completo (FQDN). Generador de topología usa nombres de dominio completos, no los nombres de host. Por lo tanto, debe configurar un sufijo DNS en el nombre del equipo para implementarse como servidor perimetral que no está unido a un dominio. **Use solo caracteres estándar** (incluidos A-z, a-z, 0-9 y guiones) al asignar los FQDN para los servidores que ejecutan Skype para Business Server. No utilice caracteres Unicode ni de subrayado. Los caracteres no estándar en una dirección URL o un FQDN a menudo no son compatibles con DNS externas y CA públicas (es decir, cuando el FQDN debe asignarse al SN en el certificado).
  
Además de una dirección IP, el FQDN se pudo asignar a una **dirección VIP** : una dirección IP virtual. Una VIP es una dirección IP que no se corresponde con una interfaz de red físico real. Una dirección VIP a menudo apunta a un grupo de servidores que realizan una función de servidor, o a un par de servidores configurados para redundancia y tolerancia a errores.
  
Hay varios tipos de registro DNS, los que son más relevantes para esta discusión son: 
  
- **A** — un registro de dirección o el registro de Host, devuelve una dirección IPv4 de 32 bits. Se usa con más frecuencia para asignar nombres de host a una dirección IP del host.
    
- **AAAA** : un registro de dirección IPv6. Devuelve una dirección IPv6 de 128 bits. Se usa con más frecuencia para asignar nombres de host a una dirección IP del host.
    
- **CNAME** : un registro de nombre canónico. Se resuelve el nombre de uno a otro: la búsqueda de DNS se volverá a intentar la búsqueda con el nuevo nombre.
    
- **SRV** : un registro de servicio (SRV registro) especifica un servicio (un proceso en un servidor) que se tiene acceso en un puerto específico y la combinación de IP. Los nombres de servicios que requieren un registro de servicio son fijos y no se puede personalizar más allá de lo que forma parte de su dominio SIP. Algunos servicios de usuario use direcciones URL sencillas. Un registro SRV debe apuntar a una ubicación en el mismo dominio SIP, por lo que si tiene varios dominios que necesitará varios registros SRV para un servicio determinado.
    
## <a name="how-to-choose-a-sip-domain-name"></a>Cómo elegir un nombre de dominio SIP
<a name="BK_NameSIP"> </a>

Nombre de dominio SIP de la organización normalmente se alinea con las direcciones de correo electrónico que se conceden a sus usuarios. Si un usuario de la organización tendría una dirección de correo electrónico como Brown@contoso.com, el preferido \<dominio sip\> para una organización con el dominio contoso.com nombre es simplemente contoso.com.
  
### <a name="multiple-sip-domains"></a>Varios dominios SIP

 En algunos casos, su organización puede necesitar varios dominios SIP. Por ejemplo, si se ha adquirido Fabrikam.com por contoso.com, es posible que necesita crear un nuevo dominio SIP que Skype para Business Server reconoce y aceptará conexiones de. En este caso, sería necesario crear un conjunto adicional de todos los registros DNS que utilice contoso.com, con el nuevo FQDN que se muestran dónde enviar solicitudes de Fabrikam.
  
## <a name="dns-load-balancing"></a>Equilibrio de carga de DNS
<a name="BK_NameSIP"> </a>

Puede usar DNS para compartir la carga de tráfico entre varios servidores que estén configurados como un grupo de servidores. Para ello, debe crear varios registros para el FQDN del grupo, cada uno de los cuales apunta a la dirección IP de un nodo en el grupo de servidores.
  
Para obtener explicaciones adicionales de equilibrio de carga, vea [Equilibrio de carga de DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) .
  

