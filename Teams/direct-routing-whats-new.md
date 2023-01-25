---
title: Novedades del enrutamiento directo
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: En este artículo se describen las novedades de enrutamiento directo. Vuelve a comprobarlo con frecuencia si hay actualizaciones.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 87befd2ff63fc5e3f0aa9e1c715972e5061b8fc7
ms.sourcegitcommit: e09591a0df9848b50bfeda29650e91e9d35724af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2023
ms.locfileid: "69981875"
---
# <a name="whats-new-for-direct-routing"></a>Novedades del enrutamiento directo

En este artículo se describen las novedades de enrutamiento directo. Vuelve a comprobarlo con frecuencia si hay actualizaciones.

## <a name="new-direct-routing-sip-endpoints"></a>Nuevos puntos de conexión SIP de enrutamiento directo 

Microsoft presentará nuevos IP de señalización para los puntos de conexión SIP de enrutamiento directo de Teams. Para asegurarse de que este cambio no afecta a la disponibilidad del servicio, asegúrese de que el controlador de borde de sesión y el firewall están configurados para usar las subredes recomendadas 52.112.0.0/14 y 52.120.0.0/14 para las reglas de clasificación y ACL. Para obtener más información, consulte [Entornos GCC de Microsoft 365, Office 365 y Office 365](direct-routing-plan.md#microsoft-365-office-365-and-office-365-gcc-environments).  

## <a name="trunk-demoting-logic-based-on-sip-options"></a>Trunk demoting logic based on SIP Options

Una nueva característica basada en las opciones del SIP se introduce para el estado del tronco. Cuando está habilitada en la configuración de la puerta de enlace (consulte Set-CsOnlinePSTNGateway cmdlet y parámetro SendSipOptions), la lógica de enrutamiento para las llamadas salientes disminuirá el nivel de los troncos que no envían opciones SIP periódicamente (el período esperado es una opción SIP enviada por el SBC por minuto) al back-end de Microsoft. Estos troncos degradados se ponen al final de la lista de trunks disponibles para la llamada saliente y se intentan como los últimos; por lo tanto, podría reducir el tiempo de configuración de la llamada.
Cualquier tronco habilitado para esa característica que no envíe al menos una opción SIP dentro de cinco minutos a cualquiera de los servidores proxy SIP regionales de Microsoft (NOAM, EMEA, APAC, OCEA) se considera degradado. Si un tronco envía opciones SIP solo a un subconjunto de servidores proxy sip regionales de Microsoft, estas rutas se prueban primero y el resto se degradan.


## <a name="sip-support"></a>Compatibilidad con SIP

El 1 de junio de 2022, Microsoft quitará la compatibilidad con fqdN de sip-all.pstnhub.microsoft.com y sip-all.pstnhub.gov.teams.microsoft.us de la configuración de enrutamiento directo.

Si no se realiza ninguna acción antes del 1 de junio, los usuarios no podrán realizar ni recibir llamadas a través del enrutamiento directo.

Para evitar el impacto en el servicio:

- Utilice las subredes recomendadas: (52.112.0.0/14 y 52.122.0.0/15) para cualquier clasificación o reglas ACL.
- Deje de usar el FQDN de sip-all al configurar los controles de borde de sesión para el enrutamiento directo.

Para obtener más información, consulte [Planear el enrutamiento directo](direct-routing-plan.md).

## <a name="tls-certificates"></a>Certificados TLS

Microsoft 365 está actualizando Teams y otros servicios para usar un conjunto diferente de entidades de certificación raíz (CA).

Para obtener más información y una lista completa de los servicios afectados, consulte [Cambios de certificados TLS en los servicios de Microsoft 365, incluido Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676).

## <a name="certificate-authorities"></a>Entidades emisoras de certificados

A partir del 1 de febrero de 2022, la interfaz SIP de enrutamiento directo solo confiará en certificados firmados por entidades de certificación (CA) que forman parte del Programa de certificados raíz de confianza de Microsoft. Siga estos pasos para evitar el impacto en el servicio:

- Asegúrese de que su certificado SBC esté firmado por una CA que formen parte del Programa de certificados raíz de confianza de Microsoft.
- Compruebe que la extensión de uso extendido de claves (EKU) del certificado incluya "Autenticación de servidor".

Para obtener más información sobre el Programa de certificados raíz de confianza de Microsoft, consulte [Requisitos del programa: programa raíz de confianza de Microsoft](/security/trusted-root/program-requirements).

Para obtener una lista de CA de confianza, consulte [Lista de certificados de CA incluidos de Microsoft](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT).

## <a name="replace-headers"></a>Reemplazar encabezados

A partir de abril de 2022, el enrutamiento directo rechazará solicitudes SIP que tengan encabezados Replaces definidos. No hay cambios en los flujos en los que Microsoft envía el encabezado Replaces al controlador de borde de sesión (SBC).

Compruebe las configuraciones de SBC y asegúrese de que no está usando los encabezados Replaces en las solicitudes SIP.

## <a name="tls10-and-11"></a>TLS1.0 y 1.1

Para proporcionar el mejor cifrado de su clase a nuestros clientes, Microsoft planea desusar las versiones 1.0 y 1.1 de la Seguridad de la capa de transporte (TLS). El 3 de abril de 2022, Microsoft forzará el uso de TLS1.2 para la interfaz SIP de enrutamiento directo.

Para evitar cualquier impacto en el servicio, asegúrese de que sus SBCs están configurados para admitir TLS1.2 y puede conectarse mediante uno de los siguientes conjuntos de cifrado:

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 es decir, ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 es decir, ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 es decir, ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 es decir, ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>Temas relacionados

- [Enrutamiento directo: protocolo SIP](direct-routing-protocols-sip.md)
