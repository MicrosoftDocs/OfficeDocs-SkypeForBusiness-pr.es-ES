---
title: Cifrado para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype empresarial Server usa TLS y MTLS para cifrar los mensajes instantáneos. Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o de si cruza el perímetro de la red interna. Al conectar Skype empresarial Server con sistemas de IPPBX de terceros o con troncos SIP, TLS es opcional, pero se recomienda encarecidamente entre el servidor de mediación y la puerta de enlace multimedia. Si en este vínculo está configurado TLS, se requiere MTLS. Por lo tanto, la puerta de enlace debe estar configurada con un certificado de una entidad emisora de confianza en el servidor de mediación.
ms.openlocfilehash: 3aadc51dff7fafe32ea929cdec3d4f2f03ee92fa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296920"
---
# <a name="encryption-for-skype-for-business-server"></a>Cifrado para Skype empresarial Server
 
Skype empresarial Server usa TLS y MTLS para cifrar los mensajes instantáneos. Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o de si cruza el perímetro de la red interna. Al conectar Skype empresarial Server a sistemas IPPBX de terceros o a troncos SIP, TLS es opcional, pero se recomienda encarecidamente entre el servidor de mediación y la puerta de enlace multimedia. Si en este vínculo está configurado TLS, se requiere MTLS. Por lo tanto, la puerta de enlace debe estar configurada con un certificado de una entidad emisora de confianza en el servidor de mediación.
  
> [!NOTE]
> En 2014 se publicó un aviso de seguridad sobre SSL 3.0. Deshabilitar SSL 3,0 en Skype empresarial Server 2015 es una opción admitida. Para obtener más información sobre el asesoramiento de seguridad, consulte [deshabilitar SSL 3,0 en Lync Server 2013 y Skype empresarial server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).<br/>
**Nota de seguridad:** Para asegurarse de que se usa el protocolo criptográfico más sólido, Skype empresarial Server 2015 ofrecerá protocolos de cifrado TLS en el siguiente orden a los clientes: **tls 1,2, tls 1,1, tls 1,0**. TLS es un aspecto crítico de Skype empresarial Server 2015 y, por lo tanto, es necesario para mantener un entorno compatible.<br/>
**Nota de seguridad:** Para asegurarse de que se usa el protocolo criptográfico más sólido, Skype empresarial Server 2019 ofrecerá protocolos de cifrado TLS en el siguiente orden a los clientes: **tls 1,3, tls 1,2**. TLS es un aspecto crítico de Skype empresarial Server 2019 y, por lo tanto, es necesario para mantener un entorno compatible. 
  
En la tabla siguiente se resumen los requisitos de protocolo para cada tipo de tráfico. 
  
**Protección de tráfico**

|**Tipo de tráfico**|**Protegido por**|
|:-----|:-----|
|Servidor a servidor  <br/> |MTLS  <br/> |
|Cliente a servidor  <br/> |TLS  <br/> |
|Mensajería instantánea y presencia  <br/> |TLS   <br/> |
|Audio, vídeo y uso compartido de escritorio  <br/> |SRTP  <br/> |
|Uso compartido de escritorio (señalización)  <br/> |TLS  <br/> |
|Conferencia web  <br/> |TLS  <br/> |
|Descarga del contenido de las reuniones, descarga de la libreta de direcciones y expansión de grupos de distribución  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>Cifrado de medios

El tráfico de medios se cifra mediante RTP seguro (SRTP), que es un perfil de protocolo de transporte en tiempo real (RTP) que proporciona al tráfico RTP confidencialidad, autenticación y protección contra los ataques de reproducción. Además, los medios que fluyen en ambas direcciones entre el servidor de mediación y el servidor interno del próximo salto también se cifran mediante SRTP. Los medios que fluyen en ambas direcciones entre el servidor de mediación y una puerta de enlace multimedia se cifran de manera opcional, pero recomendable. El servidor de mediación puede admitir el cifrado hacia la puerta de enlace multimedia, pero la puerta de enlace debe admitir MTLS y el almacenamiento de un certificado.
  
> [!NOTE]
> Para obtener más información acerca de la configuración híbrida, consulte [planear la conectividad híbrida](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
  
## <a name="fips"></a>FIPS

Skype empresarial Server y Microsoft Exchange Server 2016 funcionan con compatibilidad con algoritmos estándar de procesamiento de información federal (FIPS) 140-2 si los sistemas operativos de Windows Server están configurados para usar los algoritmos FIPS 140-2 para el cifrado de sistema . Para implementar la compatibilidad con FIPS, debe configurar cada servidor que ejecute Skype empresarial Server para que sea compatible con él.
  

