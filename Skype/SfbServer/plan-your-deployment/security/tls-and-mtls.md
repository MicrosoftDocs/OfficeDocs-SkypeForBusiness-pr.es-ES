---
title: TLS y MTLS para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Los protocolos seguridad de la capa de transporte (TLS) y seguridad de la capa de transporte mutua (MTLS) proporcionan comunicaciones cifradas y autenticación de extremos en Internet. Skype Empresarial Server estos dos protocolos para crear la red de servidores de confianza y para garantizar que todas las comunicaciones a través de esa red estén cifradas. Todas las comunicaciones SIP entre servidores se producen a través de MTLS. Las comunicaciones SIP de cliente a servidor se producen a través de TLS.
ms.openlocfilehash: 156abf52ba4274666a2783e9968b9a7ee06a29aa
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627832"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS y MTLS para Skype Empresarial Server
 
Los protocolos seguridad de la capa de transporte (TLS) y seguridad de la capa de transporte mutua (MTLS) proporcionan comunicaciones cifradas y autenticación de extremos en Internet. Skype Empresarial Server estos dos protocolos para crear la red de servidores de confianza y para garantizar que todas las comunicaciones a través de esa red estén cifradas. Todas las comunicaciones SIP entre servidores se producen a través de MTLS. Las comunicaciones SIP de cliente a servidor se producen a través de TLS.
  
TLS permite a los usuarios, a través de su software cliente, autenticar los Skype Empresarial Server a los que se conectan. En una conexión TLS, el cliente solicita un certificado válido del servidor. Para ser válido, el certificado debe haber sido emitido por una CA de confianza para el cliente y el nombre DNS del servidor debe coincidir con el nombre DNS del certificado. Si el certificado es válido, el cliente usa la clave pública del certificado para cifrar las claves de cifrado simétricas que se usarán para la comunicación, por lo que solo el propietario original del certificado puede usar su clave privada para descifrar el contenido de la comunicación. La conexión resultante es de confianza y, desde ese momento, otros servidores o clientes de confianza no lo impugnan. En este contexto, la capa de sockets seguros (SSL) que se usa con los servicios web se puede asociar como basada en TLS.
  
Las conexiones de servidor a servidor dependen de MTLS para la autenticación mutua. En una conexión MTLS, el servidor que origina un mensaje y el servidor que lo recibe intercambia certificados de una CA de confianza mutua. Los certificados prueban la identidad de cada servidor al otro. En las implementaciones de Skype Empresarial Server, todos los clientes y servidores internos consideran válidos los certificados emitidos por la CA de empresa durante su período de validez y no revocados por la CA emisora, ya que todos los miembros de un dominio de Active Directory confían en la CA de Enterprise en ese dominio. En escenarios federados, la CA emisora debe ser de confianza para ambos socios federados. Cada partner puede usar una CA diferente, si lo desea, siempre y cuando esa CA también sea de confianza para el otro partner. Esta confianza la logran con mayor facilidad los servidores perimetrales que tienen el certificado de CA raíz del asociado en sus CA raíz de confianza, o mediante el uso de una CA de terceros de confianza para ambas partes.
  
TLS y MTLS ayudan a evitar los ataques de escucha y de entrada. En un ataque man-in-the-middle, el atacante redirige las comunicaciones entre dos entidades de red a través del equipo del atacante sin el conocimiento de ninguna de las partes. La especificación TLS y Skype Empresarial Server de servidores de confianza (solo las especificadas en el Generador de topologías) mitigan el riesgo de un ataque man-in-the middle parcialmente en la capa de aplicación mediante el cifrado de extremo a extremo coordinado mediante la criptografía de clave pública entre los dos extremos, y un atacante tendría que tener un certificado válido y de confianza con la clave privada correspondiente y emitido al nombre del servicio al que se comunica el cliente para descifrar la comunicación. Sin embargo, en última instancia, debe seguir los procedimientos de seguridad recomendados con la infraestructura de red (en este caso, DNS corporativo). Skype Empresarial Server supone que el servidor DNS es de confianza del mismo modo que los controladores de dominio y los catálogos globales son de confianza, pero DNS proporciona un nivel de protección contra ataques de secuestro dns al impedir que el servidor de un atacante responda correctamente a una solicitud al nombre suplantado.
  

