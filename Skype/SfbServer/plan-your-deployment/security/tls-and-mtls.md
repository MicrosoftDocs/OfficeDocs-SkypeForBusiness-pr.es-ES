---
title: TLS y MTLS para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Los protocolos de Seguridad de la capa de transporte (TLS) y Seguridad de la capa de transporte mutua (MTLS) ofrecen comunicaciones cifradas y autenticación de extremos en Internet. Skype empresarial Server usa estos dos protocolos para crear la red de servidores de confianza y garantizar que todas las comunicaciones a través de esa red estén cifradas. Todas las comunicaciones SIP entre los servidores se llevan a cabo a través de MTLS. Las comunicaciones SIP entre el cliente y el servidor se realizan a través de TLS.
ms.openlocfilehash: 5030916780c9e39eee10bf2c2fcb6fb213c9b075
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815598"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS y MTLS para Skype empresarial Server
 
Los protocolos de Seguridad de la capa de transporte (TLS) y Seguridad de la capa de transporte mutua (MTLS) ofrecen comunicaciones cifradas y autenticación de extremos en Internet. Skype empresarial Server usa estos dos protocolos para crear la red de servidores de confianza y garantizar que todas las comunicaciones a través de esa red estén cifradas. Todas las comunicaciones SIP entre los servidores se llevan a cabo a través de MTLS. Las comunicaciones SIP entre el cliente y el servidor se realizan a través de TLS.
  
TLS permite a los usuarios, mediante el software cliente, autenticar los servidores de Skype empresarial Server a los que se conectan. En una conexión TLS, el cliente solicita un certificado válido del servidor. Para que sea válido, el certificado debe haber sido emitido por una CA que también sea de confianza para el cliente y el nombre DNS del servidor debe coincidir con el nombre DNS del certificado. Si el certificado es válido, el cliente usa la clave pública del certificado para cifrar las claves de cifrado simétricas que se utilizarán para la comunicación, de modo que solo el propietario original del certificado puede usar su clave privada para descifrar el contenido de la comunicación. La conexión resultante es fiable y desde ese punto no es desafiada por otros servidores o clientes fiables. En este contexto, SSL, tal como se usa con los servicios web, se puede asociar como basada en TLS.
  
Las conexiones entre servidores dependen de MTLS para la autenticación mutua. En una conexión MTLS, el servidor de origen de un mensaje y el que lo recibe intercambian certificados procedentes de una CA de confianza para ambos. Los certificados permiten a los servidores demostrarse mutuamente sus identidades. En las implementaciones de Skype empresarial Server, los certificados emitidos por la CA de empresa que se encuentren durante el período de validez y que no hayan sido revocados por la entidad emisora de certificados se consideren automáticamente válidos para todos los clientes y servidores internos, ya que todos los miembros de Active Directory Dominio de directorio confíe en la entidad emisora de certificados de empresa de ese dominio. En los escenarios de federación, ambos socios federados deben confiar en la CA que emite los certificados. Si así lo desea, cada socio puede utilizar una CA diferente, siempre y cuando el otro socio también confíe en esa CA. Esta confianza es más fácil para los servidores perimetrales que tienen el certificado de la entidad emisora raíz del asociado en sus entidades emisoras raíz de confianza, o mediante el uso de una CA de terceros en la que confían ambas partes.
  
TLS y MTLS ayudan a evitar los ataques de interceptación y de tipo "Man in the middle". En un ataque de intermediario, el atacante vuelve a enrutar las comunicaciones entre dos entidades de red a través del equipo del atacante sin el conocimiento de ninguna de las partes. La especificación de servidores de confianza TLS y Skype empresarial Server (solo las especificadas en el generador de topologías) reducen el riesgo de un ataque de intermediario parcialmente en el nivel de aplicación mediante el cifrado de extremo a extremo coordinado con la clave pública la criptografía entre los dos puntos de conexión y un atacante tendría que tener un certificado válido y confiable con la clave privada correspondiente y emitirse para el nombre del servicio al que se comunica el cliente para descifrar la comunicación. En todo caso, usted deberá seguir buenas prácticas de seguridad en su infraestructura de red (en este caso, DNS empresarial). Skype empresarial Server supone que el servidor DNS es de confianza de la misma forma en que se confía en los controladores de dominio y en los catálogos globales, pero DNS ofrece un nivel de protección contra ataques de secuestro DNS al impedir que el servidor de un atacante responda correctamente a una solicitud para el nombre imitado.
  

