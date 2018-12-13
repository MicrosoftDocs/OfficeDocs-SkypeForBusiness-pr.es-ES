---
title: Cifrado de Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype para Business Server usa TLS y MTLS para cifrar los mensajes instantáneos. Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o de si cruza el perímetro de la red interna. Cuando la conexión Skype para Business Server a sistemas IPPBX parte 3ª o troncos SIP TLS es opcional pero se recomienda encarecidamente entre el servidor de mediación y la puerta de enlace multimedia. Si en este vínculo está configurado TLS, se requiere MTLS. Por lo tanto, la puerta de enlace debe configurarse con un certificado de una entidad de certificación que el servidor de mediación es de confianza.
ms.openlocfilehash: ff2aa0a3d0727aa5ed579413fe03593568f9f773
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240898"
---
# <a name="encryption-for-skype-for-business-server"></a>Cifrado de Skype para Business Server
 
Skype para Business Server usa TLS y MTLS para cifrar los mensajes instantáneos. Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o de si cruza el perímetro de la red interna. Cuando la conexión Skype para Business Server a sistemas de terceros IPPBX o troncos SIP TLS es opcional pero se recomienda encarecidamente entre el servidor de mediación y la puerta de enlace multimedia. Si en este vínculo está configurado TLS, se requiere MTLS. Por lo tanto, la puerta de enlace debe configurarse con un certificado de una entidad de certificación que el servidor de mediación es de confianza.
  
> [!NOTE]
> En 2014 se publicó un aviso de seguridad sobre SSL 3.0. Deshabilitar SSL 3.0 en Skype para Business Server 2015 es una opción compatible. Para obtener más información sobre el aviso de seguridad, vea [Deshabilitar SSL 3.0 en Lync Server 2013 y Skype para Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).<br/>
**Nota de seguridad:** Para asegurarse de que se usa el protocolo de cifrado más seguro, Skype para Business Server 2015 ofrecerá los protocolos de cifrado TLS en el orden siguiente a los clientes: **1.2 TLS, TLS 1.1, TLS 1.0**. TLS es un aspecto fundamental de Skype para Business Server 2015 y, por tanto, es necesario con el fin de mantener un entorno compatible.<br/>
**Nota de seguridad:** Para asegurarse de que se usa el protocolo de cifrado más seguro, Skype para Business Server 2019 ofrecerá los protocolos de cifrado TLS en el orden siguiente a los clientes: **1.3 TLS, 1.2 de TLS**. TLS es un aspecto fundamental de Skype para Business Server 2019 y, por tanto, es necesario con el fin de mantener un entorno compatible. 
  
En la tabla siguiente se resumen los requisitos de protocolo para cada tipo de tráfico. 
  
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

El tráfico de medios se cifra mediante RTP seguro (SRTP), que es un perfil de protocolo de transporte en tiempo real (RTP) que proporciona al tráfico RTP confidencialidad, autenticación y protección contra los ataques de reproducción. Además, los medios que fluyen en ambas direcciones entre el servidor de mediación y el servidor interno del próximo salto también se cifran mediante SRTP. Los medios que fluyen en ambas direcciones entre el servidor de mediación y una puerta de enlace multimedia se cifran de manera opcional, pero recomendable. El servidor de mediación puede admitir el cifrado hacia la puerta de enlace multimedia, pero la puerta de enlace debe admitir MTLS y el almacenamiento de un certificado.
  
> [!NOTE]
> Si va a implementar un entorno híbrido, también debe modificar el Skype para el nivel de cifrado del servidor de negocio. De manera predeterminada, el nivel de cifrado es obligatorio. Debe cambiar esta configuración a compatibles mediante la Skype de consola de administración de servidor empresarial. Para obtener más información sobre la configuración híbrida, vea [Planear la conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) o [Skype para soluciones híbridas de Business Server 2019](../../../SfBServer2019/hybrid/hybrid-solutions.md) en la documentación de implementación.
  
## <a name="fips"></a>FIPS

Skype para Business Server y Microsoft Exchange Server 2016 operar con compatibilidad con Federal Information Processing Standard (FIPS) 140-2 algoritmos si los sistemas operativos Windows Server están configurados para usar el FIPS 140-2 algoritmos de criptografía de sistema . Para implementar la compatibilidad con FIPS, debe configurar cada servidor que ejecuta Skype para Business Server para que lo admitan.
  

