---
title: TLS y MTLS para Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/5/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Los protocolos de Seguridad de la capa de transporte (TLS) y Seguridad de la capa de transporte mutua (MTLS) ofrecen comunicaciones cifradas y autenticación de extremos en Internet. Skype para Business Server 2015 usa estos dos protocolos para crear la red de servidores de confianza y para garantizar que se cifran todas las comunicaciones a través de esa red. Todas las comunicaciones SIP entre los servidores se llevan a cabo a través de MTLS. Las comunicaciones SIP entre el cliente y el servidor se realizan a través de TLS.
ms.openlocfilehash: 1cc7554ab14e29fd85d2964d1323fccdfd4af604
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tls-and-mtls-for-skype-for-business-server-2015"></a>TLS y MTLS para Skype Empresarial Server 2015
 
Los protocolos de Seguridad de la capa de transporte (TLS) y Seguridad de la capa de transporte mutua (MTLS) ofrecen comunicaciones cifradas y autenticación de extremos en Internet. Skype para Business Server 2015 usa estos dos protocolos para crear la red de servidores de confianza y para garantizar que se cifran todas las comunicaciones a través de esa red. Todas las comunicaciones SIP entre los servidores se llevan a cabo a través de MTLS. Las comunicaciones SIP entre el cliente y el servidor se realizan a través de TLS.
  
TLS permite a los usuarios, a través de su software de cliente autenticar el Skype para servidores Business Server 2015 al que se conectan. En una conexión TLS, el cliente solicita un certificado desde el servidor. Para ser válido, el certificado debe haber sido emitido por una CA que también es de confianza para el cliente y el nombre DNS del servidor debe coincidir con el nombre DNS en el certificado. Si el certificado es válido, el que usa la clave pública en el certificado para cifrar el cifrado simétrico de claves que se utilizará para la comunicación, por lo que sólo el propietario original del certificado puede utilizar su clave privada para descifrar el contenido de la comunicación. La conexión resultante es de confianza y desde ese punto es desafiada por otros clientes o servidores de confianza. En este contexto, se puede asociar como TLS con Secure Sockets Layer (SSL) como se utiliza con los servicios Web.
  
Las conexiones entre servidores dependen de MTLS para la autenticación mutua. En una conexión MTLS, el servidor de origen de un mensaje y el que lo recibe intercambian certificados procedentes de una CA de confianza para ambos. Los certificados permiten a los servidores demostrarse mutuamente sus identidades. En Skype para implementaciones de servidor de negocios 2015, los certificados emitidos por la entidad emisora de certificados de empresa que están durante su validez período y no revocado por la entidad emisora se considerarán automáticamente como válidos por todos los clientes y servidores internos porque todos los miembros de un activo Directorio dominio confía en la CA de empresa de ese dominio. En los escenarios de federación, ambos socios federados deben confiar en la CA que emite los certificados. Si así lo desea, cada socio puede utilizar una CA diferente, siempre y cuando el otro socio también confíe en esa CA. Esta confianza se consigue más fácilmente los servidores de borde con el certificado de entidad emisora raíz del socio en su entidades emisoras de certificados raíz de confianza o por el uso de una CA de terceros que sea de confianza por ambas partes.
  
TLS y MTLS ayudan a evitar los ataques de interceptación y de tipo "Man in the middle". En un ataque de intermediario, el atacante redirige las comunicaciones entre dos entidades de red a través del equipo del atacante sin el conocimiento de cualquiera de las partes. TLS y Skype para Business Server 2015 especificación de servidores de confianza (sólo los especificados en el generador de topología) reducir el riesgo de un hombre en el medio del ataque parcialmente en la capa de aplicación utilizando el cifrado end-to-end coordinado mediante la clave pública la criptografía entre los dos extremos y un atacante tendría que tener un certificado válido y de confianza con la clave privada correspondiente y emitido para el nombre del servicio a la que se comunica el cliente para descifrar la comunicación. En todo caso, usted deberá seguir buenas prácticas de seguridad en su infraestructura de red (en este caso, DNS empresarial). Skype para Business Server 2015 se supone que es de confianza para el servidor DNS de la misma manera que los controladores de dominio y catálogos globales son de confianza, pero proporciona un nivel de protección contra los ataques de secuestro DNS, DNS impide que un servidor del atacante responder correctamente a una solicitud para el nombre falso.
  

