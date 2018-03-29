---
title: Cifrado para Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/15/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype para Business Server 2015 utiliza TLS y MTLS para cifrar mensajes instantáneos. Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o de si cruza el perímetro de la red interna. Cuando conecta Skype para Business Server 2015 a 3 sistemas IPPBX de fabricantes o troncos SIP TLS es opcional pero recomendado entre el servidor de mediación y la puerta de enlace multimedia. Si en este vínculo está configurado TLS, se requiere MTLS. Por lo tanto, la puerta de enlace debe configurarse con un certificado de una entidad emisora de certificados es de confianza para el servidor de mediación.
ms.openlocfilehash: bf17f2c8ff8180fa5622957c665da3f4608ca833
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="encryption-for-skype-for-business-server-2015"></a>Cifrado para Skype Empresarial Server 2015
 
Skype para Business Server 2015 utiliza TLS y MTLS para cifrar mensajes instantáneos. Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o de si cruza el perímetro de la red interna. Cuando conecta Skype para Business Server 2015 a 3 sistemas IPPBX de fabricantes o troncos SIP TLS es opcional pero recomendado entre el servidor de mediación y la puerta de enlace multimedia. Si en este vínculo está configurado TLS, se requiere MTLS. Por lo tanto, la puerta de enlace debe configurarse con un certificado de una entidad emisora de certificados es de confianza para el servidor de mediación.
  
> [!NOTE]
> En 2014 se publicó un aviso de seguridad sobre SSL 3.0. Deshabilitar SSL 3.0 en Skype para Business Server 2015 es una opción admitida. Para obtener más información sobre el documento informativo sobre seguridad, vea [Deshabilitar SSL 3.0 en Lync Server 2013 y Skype para Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/). 
  
> [! Nota de seguridad] para garantizar el protocolo cifrado más fuerte se utiliza, Skype para Business Server 2015 ofrece a los clientes protocolos de cifrado TLS en el orden siguiente: **1.2 de TLS, TLS 1.1, TLS 1.0**. TLS es un aspecto crítico de Skype para Business Server 2015 y, por tanto, es necesaria para mantener un entorno compatible. 
  
En la tabla siguiente se resumen los requisitos de protocolo para cada tipo de tráfico. 
  
**Protección del tráfico**

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

El tráfico de medios se cifra mediante RTP seguro (SRTP), que es un perfil de protocolo de transporte en tiempo real (RTP) que proporciona al tráfico RTP confidencialidad, autenticación y protección contra los ataques de reproducción. Además, los medios que fluyen en ambas direcciones entre el servidor de mediación y el servidor interno del próximo salto también se cifran mediante SRTP. Los medios que fluyen en ambas direcciones entre el servidor de mediación y una puerta de enlace multimedia se cifran de manera opcional, pero recomendable. El servidor de mediación puede admitir el cifrado hacia la puerta de enlace multimedia, pero la puerta de enlace debe admitir MTLS y el almacenamiento de un certificado.
  
> [!NOTE]
> Si está implementando un entorno híbrido, también debe modificar el Skype para el nivel de cifrado del servidor de negocios 2015. De manera predeterminada, el nivel de cifrado es obligatorio. Debe cambiar esta configuración a compatibles utilizando el Skype para el Shell de administración de servidor empresarial. Para obtener más información sobre la configuración híbrida, consulte [mover usuarios de Skype para los negocios en línea a en instalaciones](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md) en la documentación de implementación.
  
## <a name="fips"></a>FIPS

Skype para Business Server 2015 y 2016 de Microsoft Exchange Server funcione con la compatibilidad con algoritmos de Federal Information Processing Standard (FIPS) 140-2 si los sistemas operativos Windows Server están configurados para utilizar el FIPS 140-2 algoritmos de sistema criptografía. Para implementar la compatibilidad con FIPS, debe configurar cada servidor que ejecuta Skype para Business Server 2015 para soportarla.
  

