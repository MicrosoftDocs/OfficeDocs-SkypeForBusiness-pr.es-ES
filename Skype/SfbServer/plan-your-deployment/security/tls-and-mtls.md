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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Los protocolos Seguridad de la capa de transporte (TLS) y Seguridad de la capa de transporte mutua (MTLS) proporcionan comunicaciones cifradas y autenticación de extremos en Internet. Skype Empresarial Server usa estos dos protocolos para crear la red de servidores de confianza y para garantizar que todas las comunicaciones a través de esa red estén cifradas. Todas las comunicaciones SIP entre servidores se producen a través de MTLS. Las comunicaciones SIP de cliente a servidor se producen a través de TLS.
ms.openlocfilehash: 7acc75ef35a9fe9c3f155ca31f06ac38df371e37
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832020"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS y MTLS para Skype Empresarial Server
 
Los protocolos Seguridad de la capa de transporte (TLS) y Seguridad de la capa de transporte mutua (MTLS) proporcionan comunicaciones cifradas y autenticación de extremos en Internet. Skype Empresarial Server usa estos dos protocolos para crear la red de servidores de confianza y para garantizar que todas las comunicaciones a través de esa red estén cifradas. Todas las comunicaciones SIP entre servidores se producen a través de MTLS. Las comunicaciones SIP de cliente a servidor se producen a través de TLS.
  
TLS permite a los usuarios, a través de su software cliente, autenticar los servidores de Skype Empresarial Server a los que se conectan. En una conexión TLS, el cliente solicita un certificado válido al servidor. Para ser válido, el certificado debe haber sido emitido por una CA que también sea de confianza para el cliente y el nombre DNS del servidor debe coincidir con el nombre DNS del certificado. Si el certificado es válido, el cliente usa la clave pública del certificado para cifrar las claves de cifrado simétricas que se usarán para la comunicación, por lo que solo el propietario original del certificado puede usar su clave privada para descifrar el contenido de la comunicación. La conexión resultante es de confianza y, desde ese punto, otros servidores o clientes de confianza no lo prueban. En este contexto, la Capa de sockets seguros (SSL) como se usa con los servicios web se puede asociar como basada en TLS.
  
Las conexiones de servidor a servidor dependen de MTLS para la autenticación mutua. En una conexión MTLS, el servidor que origina un mensaje y el servidor que lo recibe intercambian certificados de una CA de confianza mutua. Los certificados demuestran la identidad de cada servidor al otro. En las implementaciones de Skype Empresarial Server, todos los clientes internos y servidores consideran que los certificados emitidos por la CA de empresa que están durante su período de validez y que la CA emisora no revoca son considerados automáticamente válidos por todos los clientes internos y servidores porque todos los miembros de un dominio de Active Directory confían en la CA de empresa en ese dominio. En escenarios federados, la CA emisora debe ser de confianza para ambos socios federados. Cada asociado puede usar una CA diferente, si lo desea, siempre y cuando esa CA también sea de confianza para el otro asociado. Esta confianza la logran con mayor facilidad los servidores perimetrales que tienen el certificado de ca raíz del asociado en sus CA raíz de confianza, o mediante el uso de una CA de terceros en la que ambas partes confíen.
  
TLS y MTLS ayudan a evitar ataques de interceptación y ataques de tipo "Man in the middle". En un ataque de tipo "man in the middle", el atacante vuelve a enrutar las comunicaciones entre dos entidades de red a través del equipo del atacante sin el conocimiento de ninguna de las partes. La especificación tls y Skype Empresarial Server de servidores de confianza (solo los especificados en el Generador de topologías) mitigan el riesgo de un ataque de intermediario parcialmente en el nivel de la aplicación mediante el cifrado de un extremo a otro coordinado con la criptografía de clave pública entre los dos extremos, y un atacante tendría que tener un certificado válido y de confianza con la clave privada correspondiente y emitido al nombre del servicio al que se comunica el cliente para descifrar la comunicación. En última instancia, sin embargo, debe seguir los procedimientos de seguridad recomendados con su infraestructura de red (en este caso, DNS corporativo). Skype Empresarial Server asume que el servidor DNS es de confianza de la misma manera que los controladores de dominio y los catálogos globales son de confianza, pero DNS proporciona un nivel de protección contra ataques de secuestro de DNS al impedir que el servidor de un atacante responda correctamente a una solicitud al nombre suplantado.
  

