---
title: TLS y MTLS para Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Los protocolos de Seguridad de la capa de transporte (TLS) y Seguridad de la capa de transporte mutua (MTLS) ofrecen comunicaciones cifradas y autenticación de extremos en Internet. Skype para Business Server utiliza estos dos protocolos para crear una red de servidores de confianza y para asegurarse de que se cifran todas las comunicaciones a través de esa red. Todas las comunicaciones SIP entre los servidores se llevan a cabo a través de MTLS. Las comunicaciones SIP entre el cliente y el servidor se realizan a través de TLS.
ms.openlocfilehash: b00ce2102d858db36500f78af47596677ce6d6dd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886969"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS y MTLS para Skype para Business Server
 
Los protocolos de Seguridad de la capa de transporte (TLS) y Seguridad de la capa de transporte mutua (MTLS) ofrecen comunicaciones cifradas y autenticación de extremos en Internet. Skype para Business Server utiliza estos dos protocolos para crear una red de servidores de confianza y para asegurarse de que se cifran todas las comunicaciones a través de esa red. Todas las comunicaciones SIP entre los servidores se llevan a cabo a través de MTLS. Las comunicaciones SIP entre el cliente y el servidor se realizan a través de TLS.
  
TLS permite a los usuarios, a través de su software de cliente, autenticar el Skype para servidores Business Server al que se conectan. En una conexión TLS, el cliente solicita un certificado válido del servidor. Para que sea válido, el certificado debe haber sido emitido por una CA que también sea de confianza para el cliente y el nombre DNS del servidor debe coincidir con el nombre DNS del certificado. Si el certificado es válido, el cliente usa la clave pública del certificado para cifrar las claves de cifrado simétricas que se utilizarán para la comunicación, de modo que solo el propietario original del certificado puede usar su clave privada para descifrar el contenido de la comunicación. La conexión resultante es fiable y desde ese punto no es desafiada por otros servidores o clientes fiables. En este contexto, SSL, tal como se usa con los servicios web, se puede asociar como basada en TLS.
  
Las conexiones entre servidores dependen de MTLS para la autenticación mutua. En una conexión MTLS, el servidor de origen de un mensaje y el que lo recibe intercambian certificados procedentes de una CA de confianza para ambos. Los certificados permiten a los servidores demostrarse mutuamente sus identidades. En Skype para las implementaciones de servidores empresariales, certificados emitidos por la entidad de certificación de empresa que están durante su validez período y no revocado por la entidad de certificación emisora son considerados automáticamente válidos por todos los servidores y clientes internos debido a que todos los miembros de un activo La entidad de certificación de empresa en ese dominio de confianza de dominio de Active Directory. En los escenarios de federación, ambos socios federados deben confiar en la CA que emite los certificados. Si así lo desea, cada socio puede utilizar una CA diferente, siempre y cuando el otro socio también confíe en esa CA. Esta relación de confianza se consigue más fácilmente por los servidores perimetrales tener el certificado de entidad emisora de certificados raíz del socio en su entidades de certificación raíz de confianza, o mediante el uso de una entidad emisora de certificados de terceros que sea de confianza por ambas partes.
  
TLS y MTLS ayudan a evitar los ataques de interceptación y de tipo "Man in the middle". En un ataque man-in-the-middle, el atacante redistribuye las comunicaciones entre dos entidades de red a través del equipo del atacante sin el conocimiento de cualquiera de las partes. TLS y Skype para la especificación de servidor empresarial de servidores de confianza (sólo los especificados en el generador de topología) reducir el riesgo de un ataque intermedio man in the parcialmente en el nivel de aplicación mediante el uso de cifrado de extremo a extremo coordinado mediante la clave pública criptografía entre los dos extremos y un atacante tendría que tiene un certificado válido y de confianza con la clave privada correspondiente y emitido para el nombre del servicio a la que se está comunicando el cliente para descifrar la comunicación. En todo caso, usted deberá seguir buenas prácticas de seguridad en su infraestructura de red (en este caso, DNS empresarial). Skype para Business Server se supone que es de confianza para el servidor DNS de la misma manera que los controladores de dominio y catálogos globales son de confianza, pero proporciona un nivel de protección contra los ataques de secuestro DNS, DNS impide que un servidor del atacante responder correctamente a una solicitud para el nombre falso.
  

