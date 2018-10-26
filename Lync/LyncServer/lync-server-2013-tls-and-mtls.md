---
title: TLS y MTLS para Lync Server 2013
TOCTitle: TLS y MTLS para Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59679372
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# TLS y MTLS para Lync Server 2013

 

_**Última modificación del tema:** 2013-11-07_

Los protocolos de Seguridad de la capa de transporte (TLS) y Seguridad de la capa de transporte mutua (MTLS) ofrecen comunicaciones cifradas y autenticación de extremos en Internet. Microsoft Lync Server 2013 utiliza estos dos protocolos para crear la red de servidores de confianza y garantizar que todas las comunicaciones en esa red estén cifradas. Todas las comunicaciones SIP entre los servidores se llevan a cabo a través de MTLS. Las comunicaciones SIP entre el cliente y el servidor se realizan a través de TLS.

TLS permite a los usuarios, a través de su software cliente, autenticar los servidores de Lync Server 2013 a los que se conectan. En una conexión TLS, el cliente solicita un certificado válido del servidor. Para que sea válido, el certificado debe proceder de una CA en la que también confíe el cliente y el nombre DNS del servidor debe coincidir con el nombre DNS en el certificado. Si el certificado es válido, el cliente utiliza la clave pública del certificado para cifrar las claves de cifrado simétrico que se utilizarán en la comunicación. De esta manera, solo el propietario original del certificado puede utilizar la clave privada para descifrar los contenidos de la comunicación. La conexión resultante es de confianza y, a partir de ese momento, no es desafiada por ningún otro cliente o servidor de confianza. En este contexto, el protocolo Capa de sockets seguros (SSL) usado con los servicios web puede asociarse como basado en TLS.

Las conexiones entre servidores dependen de MTLS para la autenticación mutua. En una conexión MTLS, el servidor de origen de un mensaje y el que lo recibe intercambian certificados procedentes de una CA de confianza para ambos. Los certificados permiten a los servidores demostrarse mutuamente sus identidades. En las implementaciones de Lync Server 2013 los certificados emitidos por la CA empresarial que estén dentro de su periodo de validez y no hayan sido revocados por la CA emisora serán considerados automáticamente como válidos por todos los clientes y servidores internos, ya que todos los miembros de un dominio de Active Directory confían en una CA empresarial de dicho dominio. En los escenarios de federación, ambos socios federados deben confiar en la CA que emite los certificados. Si así lo desea, cada socio puede utilizar una CA diferente, siempre y cuando el otro socio también confíe en esa CA. La manera más fácil de lograr esa confianza es configurar los servidores perimetrales para que el certificado de la CA raíz del socio figure entre sus CA raíz de confianza, o bien, usar una CA de otro fabricante en la que confíen ambas partes.

TLS y MTLS ayudan a evitar los ataques de interceptación y de tipo "Man in the middle". En los ataques de tipo "Man in the middle", el atacante enruta las comunicaciones entre dos entidades de red a través del equipo del atacante sin que lo sepa ninguna de esas entidades. El protocolo TLS y los servidores que se indiquen en Lync Server 2013 como servidores de confianza (solo aquellos especificados en Generador de topologías) mitigan el riesgo de un ataque tipo "Man in the middle" parcialmente en el nivel de la aplicación mediante cifrado de extremo a extremo coordinado con cifrado de claves públicas entre los dos extremos; para que un atacante pudiera descifrar la comunicación, debería tener un certificado válido y de confianza, así como la clave privada correspondiente emitida a nombre del servicio con el que el cliente esté comunicando. En todo caso, usted deberá seguir procedimientos de seguridad recomendados en su infraestructura de red (en este caso, DNS empresarial). Lync Server 2013 parte de la premisa de que el servidor DNS es de confianza igual que se confía en los controladores de dominios y catálogos globales, pero también es cierto que DNS ofrece un nivel de protección contra ataques de tipo secuestro, ya que evita que los servidores de los atacantes puedan responder correctamente a una solicitud del nombre suplantado.

En la siguiente figura, se muestra de manera detallada cómo Lync Server 2013 utiliza MTLS para crear una red de servidores de confianza.

**Conexiones de confianza en una red Lync Server**

![Uso de MTLS](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "Uso de MTLS")

