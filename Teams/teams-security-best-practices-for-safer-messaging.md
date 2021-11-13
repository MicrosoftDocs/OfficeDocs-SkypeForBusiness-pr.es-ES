---
title: Procedimientos recomendados de seguridad de Teams para una mensajería más segura
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 11/10/2021
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Una referencia rápida para aprender a usar Teams de forma segura, este artículo es una introducción a los procedimientos recomendados generales de seguridad y sugerencias para entrenar a los usuarios en mensajería segura.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61ba1607f2999ef56c3176d4ba8ed0aaebb82e50
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909689"
---
# <a name="security-best-practices-for-microsoft-teams"></a>Procedimientos recomendados de seguridad para Microsoft Teams

La colaboración a través de la mensajería instantánea y las videoconferencias han permitido que muchas empresas y escuelas continúen con su trabajo durante la pandemia. Sin embargo, la colaboración en tiempo real en línea a una escala tan amplia también incluye *riesgos* que se deben abordar. En caso contrario, los malos actores se aprovechan de este cambio en el trabajo y la vida con **campañas de suplantación de identidad (phishing)** y **correo no deseado**. La lista de referencias numeradas de este artículo actúa como una referencia para la seguridad general al usar Teams para enviar mensajes a otras personas y es una guía de aprendizaje para los nuevos usuarios de la seguridad de Teams o cualquier tipo de mensajería instantánea.

Los mismos riesgos de suplantación de identidad (phishing) que existen en el correo electrónico existen en las aplicaciones de mensajería instantánea y colaboración, por lo que se deben aplicar las mismas directrices y orientación del usuario para proteger a los usuarios de Teams.

A nivel de usuario, algunas medidas pueden ser sencillas y los usuarios deben sentirse seguros para confiar en ellas. Los usuarios no deben hacer clic para abrir vínculos de personas que no conozcan o cuya identidad no puedan comprobar según el artículo [Protegerse de la suplantación de identidad](https://support.microsoft.com/en-us/windows/protect-yourself-from-phishing-0c7ea947-ba98-3bd9-7184-430e1f860a44). Y para protegerse contra ataques externos, los administradores de inquilinos pueden deshabilitar o desactivar la federación empresarial y Teams for Life (TFL) y la interoperabilidad de Skype, en relación con [Administrar el acceso externo (federación): Microsoft Teams | Microsoft Docs](/microsoftteams/manage-external-access).

El conjunto de características de colaboración de Teams permiten la mensajería, los archivos colaborativos, las reuniones, las pizarras y muchas otras oportunidades para conectarse. Estas características funcionan en Teams para Enterprise, Teams for Life, Skype, cliente de Skype Empresarial, Azure Communication Services (ACS) y mucho más. Esto también significa que es necesario protegerse a uno mismo, a sus compañeros y a sus clientes en toda la extensión de estas capacidades. Aquí, de nuevo, todos los usuarios deben sentirse seguros para tomar la decisión más segura para ellos, sus compañeros y sus clientes.

## <a name="just-as-with-email-online-safety-must-be-practiced-in-microsoft-teams-messaging"></a>Al igual que con el correo electrónico, la seguridad en línea se debe practicar en la mensajería de Microsoft Teams

Las medidas de seguridad estándar se deben asentar al trabajar en Teams.

1. Tenga cuidado con los contactos y las solicitudes de reunión de fuera de su organización. Los extraños pueden ser bien intencionados. Pero algunos pueden tener intenciones dañinas en secreto.
2. Si no reconoce al remitente, puede comprobar la identidad en la lista global de direcciones conocida de su empresa y escalar las comunicaciones que no pueda comprobar a un nivel superior para su tratamiento. En caso de duda, no interactúe con usuarios desconocidos ni no registrados.
3. Si recibe un vínculo o archivo de una persona desconocida, no haga clic en él. De nuevo, use su mejor criterio para los su seguridad y la de otros usuarios, así como la de sus clientes.
4. Si un vínculo de navegación en el que ha hecho clic le remite a una página de vínculos seguros en la que se le bloquea la navegación, no intente eludir esa página (lo mismo ocurre con los datos adjuntos en los que se hace clic y que pueden terminar en una página de datos adjuntos de color rojo, bloqueando los datos adjuntos seguros). Si conoce y confía en el sitio de destino, informe del problema a Microsoft y a quien le haya dirigido allí. Pero hay muchos motivos para que una página sea bloqueada y las banderas rojas se deben tener en cuenta, en lugar de ignorarlas.
5. Nunca dé información personal a las peticiones no solicitadas. Esto también es un riesgo para la seguridad personal. Los atacantes pueden aprovechar detalles tan sencillos como su cumpleaños.
6. Escanee los vínculos en busca de faltas de ortografía, dígitos agregados o caracteres extraños. Es posible que esté esperando un vínculo a `www.litware.com/strategies/Metricsbreakout.xlsx`, pero descubra que la dirección tiene el aspecto de `www.litwre.com`, `www.litwarecom.com`, o incluso `www.litwαre.com`. Si no reconoce el vínculo, desconfíe. La dirección `www.litware.com` no es la misma que la `www.litware2021.com`.

Es importante que mantenga la vigilancia y no dé su seguridad ni la seguridad de aquellos con los que trabaja a la ligera o por sentado. Como usuarios individuales, se debe sentir siempre seguro para protegerse a sí mismo y a sus compañeros y clientes mediante verificación antes de confiar.

Por último, también es fundamental reconocer que todos cometen errores. Los usuarios son propensos a hacer clic cuando tienen prisa, por ejemplo, o cuando están cansados. Los administradores se deben asegurar de que los recursos para escalar los clics del vínculo problemático y otros incidentes de seguridad los conozcan claramente los usuarios de su organización, de modo que, si se comete un error, el usuario recurra y se puedan realizar más acciones de seguridad.

> [!TIP]
> Compruebe la tarjeta de Perfil de cualquier contacto del que no esté seguro, especialmente si el correo electrónico es externo a su empresa (por ejemplo, una cuenta que termina en *@litware.com* si su organización no es *Litware).* Un usuario puede comprobar que las personas que no conocen son invitados de bienvenida a una reunión marcando la tarjeta de Perfil para **(INVITADO)**. Se invita expresamente a los invitados a participar.