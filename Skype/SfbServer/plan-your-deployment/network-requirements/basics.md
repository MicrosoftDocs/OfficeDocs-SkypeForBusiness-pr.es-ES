---
title: Conceptos básicos DNS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 tiene software integrado que puede proporcionar servicios DNS, así que es aconsejable revisar la documentación disponible como la Guía de escenario de la política de DNS. Si lo prefiere puede elegir una solución de terceros.
ms.openlocfilehash: df6a693c50b3ca8b61baf0e47e0d019478f3cbf9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="dns-basics"></a>Conceptos básicos DNS
 
Windows Server 2016 tiene software integrado que puede proporcionar servicios DNS, así que es aconsejable revisar la documentación disponible como la [Guía de escenario de política de DNS](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/dns-policy-scenario-guide). Si lo prefiere puede elegir una solución de terceros.
  
Se recomienda se recomienda dedicar un servidor específico en la implementación para proporcionar DNS. Usted podría potencialmente Configurándolos en uno de los servidores dedicados a uno de lo Skype para funciones de servidor de la empresa, pero si ese servidor también formaba parte de un grupo y consiguió decomisado por accidente Skype para negocios serían mal funcionamiento hasta que se han restablecido los servicios DNS.
  
## <a name="dns-records"></a>Registros DNS

Cada asignación de un nombre a una dirección IP (y que podría ser una dirección IPv4 o IPv6) se almacena en un registro DNS en el servidor DNS. El nombre se describe en el informe de DNS específicamente como un FQDN, un nombre de dominio completo. Aunque *contoso.com* es un nombre de dominio válido, es una forma abreviada de * \*. contoso.com* , por lo que es ambiguo y posiblemente podría referirse a cualquier servidor en el dominio. Un ejemplo de un FQDN que haría referencia a un único servidor de su dominio podría ser **meeting01.contoso.com**.
  
> [!IMPORTANT]
> De manera predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre de host, en lugar de un nombre de dominio completo (FQDN). El generador de topología utiliza FQDN, no los nombres de host. Así pues, necesita configurar un sufijo de DNS en el nombre del equipo para poder implementarlo como servidor perimetral no incorporado a un dominio. **Utilice caracteres de un sólo estándares** (incluyendo A-z, a-z, 0-9 y guiones) al asignar nombres de dominio completos a los servidores que ejecutan Skype para Business Server. No utilice caracteres Unicode ni guiones bajos. Por lo general, los DNS externos y las entidades de certificación (CA) públicas no admiten caracteres que no sean estándares en un FQDN (es decir, cuando el FQDN se necesita asignar al nombre de sujeto en el certificado).
  
Además de una dirección IP, puede asignar el FQDN para **VIP** : una dirección IP virtual. Una VIP es una dirección IP que no se corresponde con una interfaz de red física real. VIP a menudo apunta a un grupo de servidores que realizan una función de servidor o a un par de servidores configurados para redundancia y tolerancia a errores.
  
Hay varios tipos de registro DNS, los que son más relevantes para esta discusión son: 
  
- **A** — un registro de dirección ni el registro de Host, devuelve una dirección IPv4 de 32 bits. Normalmente se utiliza para asignar nombres de host a una dirección IP del host.
    
- **AAAA** : un registro de dirección IPv6. Devuelve una dirección IPv6 de 128 bits. Normalmente se utiliza para asignar nombres de host a una dirección IP del host.
    
- **CNAME** : un registro de nombre canónico. Esto resuelve un nombre a otro: la búsqueda DNS se volverá a intentar la búsqueda con el nuevo nombre.
    
- **SRV** : un registro de servicio (registros SRV) especifica un servicio (un proceso en un servidor) que se tiene acceso en una combinación de IP y un puerto específico. Los nombres de servicios que requiere un registro de servicio son fijos y no se puede personalizar más allá de lo que forma parte de su dominio SIP. Algunos servicios de usuario utilizan direcciones URL Simple. Un registro SRV debe señalar a una ubicación en el mismo dominio SIP, así que si tiene varios dominios que necesitará varios registros SRV para un servicio determinado.
    
## <a name="how-to-choose-a-sip-domain-name"></a>Cómo elegir un nombre de dominio SIP
<a name="BK_NameSIP"> </a>

Nombre de dominio SIP de la organización normalmente se alinea con las direcciones de correo electrónico a sus usuarios. Si un usuario de la organización tendría una dirección de correo electrónico como Brown@contoso.com, el preferido \<dominio sip\> para una organización con el dominio contoso.com nombre es simplemente contoso.com.
  
### <a name="multiple-sip-domains"></a>Varios dominios SIP

 En algunos casos, su organización puede necesitar varios dominios SIP. Como ejemplo, si adquirió Fabrikam.com contoso.com, debe crear un nuevo dominio SIP que Skype para Business Server reconoce y acepta la conexión de. Al hacer esto, deberá crear un conjunto adicional de todos los registros DNS que utilice contoso.com, con nuevo FQDN que muestran dónde enviar solicitudes de Fabrikam.
  
## <a name="dns-load-balancing"></a>Equilibrio de carga de DNS
<a name="BK_NameSIP"> </a>

Puede utilizar DNS para compartir la carga de tráfico entre varios servidores configurados como un grupo de servidores. Para ello, crearía varios registros para el FQDN del grupo de servidores, cada uno de los cuales señala a la dirección IP de un nodo en el grupo.
  
Para obtener explicaciones adicionales de equilibrio de carga, vea [DNS equilibrio de carga](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) .
  

