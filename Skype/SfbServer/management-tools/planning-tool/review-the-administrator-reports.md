---
title: Revisar los informes de administrador en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: Los informes de administrador consisten en información detallada acerca de la implementación y las diversas operaciones. Los informes se generan en función de las selecciones marcadas en Sitios de diseño. El diseñador puede seguir incorporando valor agregado a los informes de administrador; para ello, puede editar los diagramas de red y definir todas las direcciones IP y los nombres de dominio completos (FQDN) de servidores, grupos y equilibradores de carga.
ms.openlocfilehash: b8c18dcfef28ac93e8c2036fee7f7b105f5c69bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823350"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Revisar los informes de administrador en Skype Empresarial Server 2015

Los informes de administrador consisten en información detallada acerca de la implementación y las diversas operaciones. Los informes se generan en función de las selecciones marcadas en **Sitios de diseño**. El diseñador puede seguir incorporando valor agregado a los informes de administrador; para ello, puede editar los diagramas de red y definir todas las direcciones IP y los nombres de dominio completos (FQDN) de servidores, grupos y equilibradores de carga.

La característica informes de administrador le permite:

- [Revisar el informe de resumen](review-the-administrator-reports.md#Summary_report)

- [Revisar el informe de certificados](review-the-administrator-reports.md#Certificates_Report)

- [Revisar el informe de firewall](review-the-administrator-reports.md#Firewall_report)

- [Revisar el informe dns](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>Revisar el informe de resumen
<a name="Summary_report"> </a>

El informe de administradores de Skype Empresarial es el primero de los cuatro informes valiosos que documentan el diseño en detalle. La información de este informe y los otros tres informes asociados son útiles para los equipos de tecnología de la información:

![Informe de administración de resumen general](../../media/General_Summary_Report_Admin_Report.png)

El informe de resumen enumera la información de configuración general asociada a la red perimetral. Se documenta la ubicación, el nombre de dominio completo (FQDN) y la dirección IP, el tipo de red y los comentarios específicos de un rol determinado.

El diseñador y cada uno de los equipos que implementarán, administrarán y mantendrán la infraestructura deben revisar el informe de resumen para ver la precisión y asegurarse de que los errores se producen como mínimo.

También puede ver informes más detallados:

- Informe de certificados

- Informe de firewall

- Informe de DNS

## <a name="review-the-certificates-report"></a>Revisar el informe de certificados
<a name="Certificates_Report"> </a>

El informe de certificados contiene todos los certificados necesarios en la implementación recomendada de Skype Empresarial Server 2015. La Herramienta de planeación tiene en cuenta los nombres de sujeto y los nombres alternativos de sujeto que se introducen. El texto predeterminado que se deja sin editar puede representar un posible desafío para el equipo responsable de solicitar y emitir los certificados. La información de certificados contiene también información sobre dónde puede emitirse normalmente el certificado. Si la infraestructura no dispone de una infraestructura de clave pública (PKI) interna, todos los certificados se pueden solicitar a través de un proveedor de certificados público. Los campos Uso mejorado de clave (EKU) y Asignar a del informe son muy útiles para comprender el objetivo y la ubicación en la que debe estar cada certificado.

![Informe de administración de certificados](../../media/Certificates_Report_Admin_Report.png)

Revise cuidadosamente y asegúrese de comprender el uso y el propósito de cada certificado en la implementación. Si hay alguna pregunta sobre lo que hace un certificado, determine con qué servidor o servicio está hablando. Los certificados de Skype Empresarial Server 2015 se usan con dos fines principales:

- Seguridad de la capa de transporte mutua (MTLS): los equipos implicados en la comunicación presentan un certificado que demuestra su identidad a otro equipo. Esto se conoce como autenticación de servidor. La comunicación no puede comenzar hasta que cada equipo confíe en la identidad del otro equipo.

- Cifrado: el cifrado (Capa de sockets seguros, SSL, Seguridad de la capa de transporte o TLS) es un medio fundamental para ayudar a proteger las comunicaciones, ayudar a garantizar la privacidad y crear un sistema de colaboración y comunicaciones de confianza.

## <a name="review-the-firewall-report"></a>Revisar el informe de firewall
<a name="Firewall_report"> </a>

Skype Empresarial Server 2015 tiene un conjunto potencialmente complejo de reglas de firewall. La Herramienta de planeación reduce esta complejidad al generar un informe que define en detalle todos los requisitos de firewall, en función de los criterios de entrada del diseñador. El administrador del firewall de TI podrá usar este informe para configurar y definir las reglas necesarias.

Desde el punto de vista de la administración del firewall, el informe debe revisarse cuidadosamente para asegurarse de que no haya conflictos con la salida de reglas de firewall y de que no haya directivas o procedimientos que puedan infringirse.

![Informe de administración de firewall](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>Revisar el informe dns
<a name="DNS_Report"> </a>

El informe DNS, que forma parte del informe de administrador, detalla todas las entradas recomendadas y conocidas para el Sistema de nombres de dominio (DNS) en las redes internas, perimetrales y externas. Si el diseñador ha completado las ediciones del diagrama de red y todas las direcciones IP y los nombres de dominio completos (FQDN) se definen en sus valores de producción, el informe de DNS proporciona un recurso de configuración excelente. Este informe también puede servir como documento de solución de problemas operativos.

![Informe de administración de DNS](../../media/DNS_Report_Admin_Report.png)

Debe hacer que el equipo de administración de DNS revise exhaustivamente el informe de DNS para asegurarse de que no haya errores que puedan causar dificultades durante la implementación o que puedan complicar una sesión de solución de problemas.

## <a name="see-also"></a>Vea también
<a name="DNS_Report"> </a>

[Revisión de los informes del administrador](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
