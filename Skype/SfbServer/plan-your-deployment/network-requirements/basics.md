---
title: Conceptos básicos sobre DNS
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 tiene software integrado que puede proporcionar servicios DNS, por lo que es posible que quieras revisar la documentación disponible, como la Guía de escenarios de directivas DNS. Puedes elegir una solución de terceros si lo prefieres.
ms.openlocfilehash: 2e8655cb53228fbfe23bc62aaebbdfd5a02ce4f4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116038"
---
# <a name="dns-basics"></a>Conceptos básicos sobre DNS
 
Windows Server 2016 tiene software integrado que puede proporcionar servicios DNS, por lo que es posible que quieras revisar la documentación disponible, como la Guía de escenarios de directiva [DNS.](/windows-server/networking/dns/deploy/dns-policy-scenario-guide) Puedes elegir una solución de terceros si lo prefieres.
  
Se recomienda que, como procedimiento recomendado, dedique un servidor específico a la implementación para proporcionar DNS. Potencialmente, podría configurarlo en uno de los servidores dedicados a uno de los roles de servidor de Skype Empresarial, pero si ese servidor también formaba parte de un grupo de servidores y se retirara por accidente Skype Empresarial no funcionaría correctamente hasta que se vuelvan a establecer los servicios DNS.
  
## <a name="dns-records"></a>Registros de DNS

Cada asignación de un nombre a una dirección IP (y que podría ser una dirección IPv4 o IPv6) se almacena en un registro DNS en el servidor DNS. El nombre se describe en el informe DNS específicamente como un FQDN, un nombre de dominio completo. Aunque *contoso.com* es un nombre de dominio válido, es abreviada para *\* .contoso.com* , por lo que es ambiguo y puede hacer referencia a cualquier servidor del dominio. Un ejemplo de FQDN que haga referencia a un único servidor de su dominio puede ser **meeting01.contoso.com**.
  
> [!IMPORTANT]
> De forma predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre de host y no un nombre de dominio completo (FQDN). El Generador de topologías usa FQDN, no nombres de host. Así pues, debe configurar un sufijo de DNS en el nombre del equipo para poder implementarlo como servidor perimetral no incorporado a un dominio. **Use solo** caracteres estándar (incluidos A-Z, a-z, 0-9 y guiones) al asignar FQDN a los servidores que ejecutan Skype Empresarial Server. No utilice caracteres Unicode ni de subrayado. Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (es decir, cuando el FQDN se debe asignar al nombre de sujeto en el certificado).
  
Además de una dirección IP, el FQDN podría asignarse a una **DIRECCIÓN VIP:** una dirección IP virtual. Una VIP es una dirección IP que no corresponde a una interfaz de red física real. A menudo, una VIP apunta a un grupo de servidores que realizan un rol de servidor o a un par de servidores configurados para redundancia y tolerancia a errores.
  
Hay varios tipos de registro DNS, los que son más relevantes para esta discusión son: 
  
- **A:** un registro de dirección o un registro host, devuelve una dirección IPv4 de 32 bits. Más comúnmente se usa para asignar nombres de host a una dirección IP del host.
    
- **AAAA:** un registro de direcciones IPv6. Devuelve una dirección IPv6 de 128 bits. Más comúnmente se usa para asignar nombres de host a una dirección IP del host.
    
- **CNAME:** un registro de nombre canónico. Esto resuelve un nombre a otro: la búsqueda DNS volverá a intentar la búsqueda con el nuevo nombre.
    
- **SRV:** un registro de servicio (registro SRV) especifica un servicio (un proceso en un servidor) al que se tiene acceso en una combinación específica de puerto e IP. Los nombres de los servicios que requieren un registro de servicio son fijos y no se pueden personalizar más allá de hacerlos parte del dominio SIP. Algunos servicios de usuario usan direcciones URL sencillas. Un registro SRV debe apuntar a una ubicación en el mismo dominio SIP, por lo que si tiene varios dominios, necesitará varios registros SRV para un servicio determinado.
    
## <a name="how-to-choose-a-sip-domain-name"></a>Cómo elegir un nombre de dominio SIP
<a name="BK_NameSIP"> </a>

El nombre de dominio SIP de una organización normalmente se alinea con las direcciones de correo electrónico dadas a sus usuarios. Si un usuario de la organización tendría una dirección de correo electrónico como Brown@contoso.com, lo preferido para una organización con el nombre de dominio contoso.com es \<sip-domain\> simplemente contoso.com.
  
### <a name="multiple-sip-domains"></a>Varios dominios SIP

 En algunos casos, es posible que su organización necesite varios dominios SIP. Por ejemplo, si Fabrikam.com adquirió contoso.com, es posible que deba crear un nuevo dominio SIP que Skype Empresarial Server reconozca y acepte la conexión. Al hacerlo, deberá crear un conjunto adicional de todos los registros DNS que usan contoso.com, con nuevos FQDN que muestran dónde enviar solicitudes para Fabrikam.
  
## <a name="dns-load-balancing"></a>Equilibrio de carga de DNS
<a name="BK_NameSIP"> </a>

Puede usar DNS para compartir la carga de tráfico entre varios servidores configurados como un grupo de servidores. Para ello, crearía varios registros A para el FQDN del grupo, cada uno de los cuales apunta a la dirección IP de un nodo del grupo.
  
Consulte [Equilibrio de carga DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) para obtener más información sobre el equilibrio de carga.
