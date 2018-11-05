---
title: Revisión del informe de certificados en Lync Server 2013
TOCTitle: Revisión del informe de certificados en Lync Server 2013
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558651(v=OCS.15)
ms:contentKeyID: 52061639
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Revisión del informe de certificados en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

El informe Certificados contiene todos los certificados necesarios en la implementación recomendada de Lync Server 2013. La Herramienta de planeación controla los nombres de sujeto y los nombres alternativos del sujeto que se especifican. El texto predeterminado que se deja sin editar puede representar un posible desafío para el equipo responsable de solicitar y emitir los certificados. La información del certificado también contiene datos sobre el origen desde el cual puede emitirse normalmente el certificado. Si la infraestructura no dispone de una infraestructura de clave pública (PKI) interna, todos los certificados se pueden solicitar a través de un proveedor de certificados público. Los campos Uso mejorado de clave (EKU) y Asignar a del informe son muy útiles para comprender el objetivo y la ubicación de cada certificado.

![Informe de administración de certificados](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Informe de administración de certificados")

Revise con atención y comprenda completamente el uso y el propósito de cada certificado de la implementación. Si tiene alguna pregunta acerca de la función de un certificado, determine los elementos con los que se comunica un servidor o servicio. Los certificados de Lync Server 2013 se usan para dos fines principales:

  - Seguridad de la capa de transporte mutua (MTLS): los equipos que participan en la comunicación presentan un certificado que prueba su identidad al otro equipo; esto se conoce como autenticación del servidor. La comunicación no puede comenzar hasta que ambos equipos confíen mutuamente en la identidad del otro.

  - Cifrado: el cifrado (Capa de sockets seguros, o SSL, y Seguridad de la capa de transporte, o TLS) es un medio fundamental para proteger las comunicaciones y la privacidad, así como para crear comunicaciones de confianza y un sistema de colaboración.

## Vea también

#### Otros recursos

[Revisión de los informes del administrador en Lync Server 2013](lync-server-2013-reviewing-the-administrator-reports.md)

