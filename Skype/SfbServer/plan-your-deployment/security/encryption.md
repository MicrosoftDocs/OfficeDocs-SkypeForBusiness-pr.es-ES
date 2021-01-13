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
description: Skype Empresarial Server usa TLS y MTLS para cifrar mensajes instantáneos. Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o atraviesa el perímetro de la red interna. Al conectar Skype Empresarial Server a sistemas IPPBX de terceros o troncos SIP TLS es opcional, pero se recomienda encarecidamente entre el servidor de mediación y la puerta de enlace de medios. Si TLS está configurado en este vínculo, se requiere MTLS. Por lo tanto, la puerta de enlace debe configurarse con un certificado de una CA de confianza para el servidor de mediación.
ms.openlocfilehash: 48af03d7f6aed5b744ad4e0c460622194a87d96e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832210"
---
# <a name="encryption-for-skype-for-business-server"></a>Cifrado para Skype Empresarial Server
 
Skype Empresarial Server usa TLS y MTLS para cifrar mensajes instantáneos. Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o atraviesa el perímetro de la red interna. Al conectar Skype Empresarial Server a sistemas IPPBX de terceros o troncos SIP TLS es opcional, pero se recomienda encarecidamente entre el servidor de mediación y la puerta de enlace de medios. Si TLS está configurado en este vínculo, se requiere MTLS. Por lo tanto, la puerta de enlace debe configurarse con un certificado de una CA de confianza para el servidor de mediación.
  
> [!NOTE]
> En 2014 se publicó un aviso de seguridad sobre SSL 3.0. Deshabilitar SSL 3.0 en Skype Empresarial Server 2015 es una opción compatible. Para obtener más información sobre el aviso de seguridad, consulte [Deshabilitar SSL 3.0 en Lync Server 2013 y Skype Empresarial Server 2015.](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)<br/>
**Nota de seguridad:** Para asegurarse de que se usa el protocolo criptográfico más seguro, Skype Empresarial Server 2015 ofrecerá protocolos de cifrado TLS en el siguiente orden a los clientes: **TLS 1.2 , TLS 1.1, TLS 1.0.** TLS es un aspecto crítico de Skype Empresarial Server 2015 y, por lo tanto, es necesario para mantener un entorno compatible.<br/>
**Nota de seguridad:** Para asegurarse de que se usa el protocolo criptográfico más seguro, Skype Empresarial Server 2019 ofrecerá protocolos de cifrado TLS en el siguiente orden a los clientes: **TLS 1.3, TLS 1.2.** TLS es un aspecto fundamental de Skype Empresarial Server 2019 y, por lo tanto, es necesario para mantener un entorno compatible. 
  
En la tabla siguiente, se resumen los requisitos de protocolo para cada tipo de tráfico. 
  
**Protección de tráfico**

|**Tipo de tráfico**|**Protegido por**|
|:-----|:-----|
|De servidor a servidor  <br/> |MTLS  <br/> |
|Cliente a servidor  <br/> |TLS  <br/> |
|Mensajería instantánea y presencia  <br/> |TLS  <br/> |
|Audio, vídeo y uso compartido de escritorio  <br/> |SRTP  <br/> |
|Uso compartido de escritorio (señalización)  <br/> |TLS  <br/> |
|Conferencia web  <br/> |TLS  <br/> |
|Descarga del contenido de las reuniones, descarga de la libreta de direcciones y expansión de grupos de distribución  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>Cifrado de medios

El tráfico de medios se cifra mediante RTP seguro (SRTP), que es un protocolo de transporte en tiempo real (RTP) que proporciona al tráfico RTP confidencialidad, autenticación y protección contra los ataques de reproducción. Además, el contenido multimedia que fluye en ambas direcciones entre el servidor de mediación y el próximo salto interno también se cifra con SRTP. Los medios que fluyen en ambas direcciones entre el servidor de mediación y una puerta de enlace de medios se cifran y se recomiendan opcionalmente. El servidor de mediación puede admitir el cifrado de los medios que fluyen hacia la puerta de enlace multimedia, pero la puerta de enlace debe admitir MTLS y el almacenamiento de un certificado.
  
> [!NOTE]
> Para obtener más información acerca de la configuración híbrida, vea [Planear la conectividad híbrida.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)
  
## <a name="fips"></a>FIPS

Skype Empresarial Server y Microsoft Exchange Server 2016 funcionan con compatibilidad con algoritmos del Estándar federal de procesamiento de información (FIPS) 140-2 si los sistemas operativos Windows Server están configurados para usar los algoritmos FIPS 140-2 para la criptografía del sistema. Para implementar la compatibilidad con FIPS, debe configurar cada servidor que ejecute Skype Empresarial Server para que lo admita.
  

