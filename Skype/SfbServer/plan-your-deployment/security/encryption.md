---
title: Cifrado para Skype Empresarial Server
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
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype Empresarial Server usa TLS y MTLS para cifrar mensajes instantáneos. Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o si atraviesa el perímetro de red interno. Al conectar Skype Empresarial Server a sistemas IPPBX de terceros o troncos SIP TLS es opcional, pero se recomienda encarecidamente entre el servidor de mediación y la puerta de enlace multimedia. Si TLS está configurado en este vínculo, se requiere MTLS. Por lo tanto, la puerta de enlace debe configurarse con un certificado de una CA de confianza del servidor de mediación.
ms.openlocfilehash: 269a5394f5438802c68dabed17081c71a353a2b5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104236"
---
# <a name="encryption-for-skype-for-business-server"></a>Cifrado para Skype Empresarial Server
 
Skype Empresarial Server usa TLS y MTLS para cifrar mensajes instantáneos. Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o si atraviesa el perímetro de red interno. Al conectar Skype Empresarial Server a sistemas IPPBX de terceros o troncos SIP TLS es opcional, pero se recomienda encarecidamente entre el servidor de mediación y la puerta de enlace multimedia. Si TLS está configurado en este vínculo, se requiere MTLS. Por lo tanto, la puerta de enlace debe configurarse con un certificado de una CA de confianza del servidor de mediación.
  
> [!NOTE]
> En 2014 se publicó un aviso de seguridad sobre SSL 3.0. Deshabilitar SSL 3.0 en Skype Empresarial Server 2015 es una opción compatible. Para obtener más información sobre el asesoramiento de seguridad, vea [Deshabilitar SSL 3.0 en Lync Server 2013 y Skype Empresarial Server 2015](/archive/blogs/uclobby/disabling-ssl-3-0-in-lync-server-2013).<br/>
**Nota de seguridad:** Para asegurarse de que se usa el protocolo criptográfico más seguro, Skype Empresarial Server 2015 ofrecerá protocolos de cifrado TLS en el siguiente orden a los clientes: **TLS 1.2 , TLS 1.1, TLS 1.0**. TLS es un aspecto crítico de Skype Empresarial Server 2015 y, por lo tanto, es necesario para mantener un entorno compatible.<br/>
**Nota de seguridad:** Para asegurarse de que se usa el protocolo criptográfico más seguro, Skype Empresarial Server 2019 ofrecerá protocolos de cifrado TLS en el siguiente orden a los clientes: **TLS 1.3, TLS 1.2**. TLS es un aspecto crítico de Skype Empresarial Server 2019 y, por lo tanto, es necesario para mantener un entorno compatible. 
  
En la tabla siguiente, se resumen los requisitos de protocolo para cada tipo de tráfico. 
  
**Protección de tráfico**

|**Tipo de tráfico**|**Protegido por**|
|:-----|:-----|
|Servidor a servidor  <br/> |MTLS  <br/> |
|Cliente a servidor  <br/> |TLS  <br/> |
|Mensajería instantánea y presencia  <br/> |TLS  <br/> |
|Audio, vídeo y uso compartido de escritorio  <br/> |SRTP  <br/> |
|Uso compartido de escritorio (señalización)  <br/> |TLS  <br/> |
|Conferencia web  <br/> |TLS  <br/> |
|Descarga del contenido de las reuniones, descarga de la libreta de direcciones y expansión de grupos de distribución  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>Cifrado de medios

El tráfico de medios se cifra mediante RTP seguro (SRTP), que es un protocolo de transporte en tiempo real (RTP) que proporciona al tráfico RTP confidencialidad, autenticación y protección contra los ataques de reproducción. Además, el contenido multimedia que fluye en ambas direcciones entre el servidor de mediación y el próximo salto interno también se cifra con SRTP. Los medios que fluyen en ambas direcciones entre el servidor de mediación y una puerta de enlace multimedia se cifran y se recomiendan opcionalmente. El servidor de mediación puede admitir el cifrado de los medios que fluyen hacia la puerta de enlace multimedia, pero la puerta de enlace debe admitir MTLS y el almacenamiento de un certificado.
  
> [!NOTE]
> Para obtener más información acerca de la configuración híbrida, vea [Plan hybrid connectivity](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
  
## <a name="fips"></a>FIPS

Skype Empresarial Server y Microsoft Exchange Server 2016 funcionan con compatibilidad con los algoritmos 140-2 del Estándar federal de procesamiento de información (FIPS) si los sistemas operativos Windows Server están configurados para usar los algoritmos FIPS 140-2 para criptografía del sistema. Para implementar la compatibilidad con FIPS, debe configurar cada servidor que ejecute Skype Empresarial Server para admitirlo.
