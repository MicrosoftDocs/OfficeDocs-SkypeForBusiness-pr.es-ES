---
title: Optimizar su entorno actual de Skype Empresarial para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Guía para que inicie el recorrido desde Skype Empresarial a Microsoft Teams."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cae04416438d08771324b5227014ab4f3043a71
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
<a name="optimize-your-current-skype-for-business-environment-for-microsoft-teams"></a>Optimizar su entorno actual de Skype Empresarial para Microsoft Teams
==============================================================

Todo cambio lleva tiempo. Su organización tiene que considerar los ciclos de vida de la implementación, la planeación de recursos y la administración de cambios. Por nuestra parte, nos esforzamos para que Microsoft Teams cumpla todas sus necesidades a largo plazo. Mientras lo logramos, mostramos algunas de las cosas que puede empezar a hacer para prepararse. Si finaliza esta guía, podrá llevar a cabo la implementación de Microsoft Teams correctamente en su organización.

## <a name="environmental-readiness"></a>Preparación del entorno


La siguiente guía se debe usar para garantizar que la implementación de Microsoft Teams se realice correctamente. Con ella podrá validar su entorno actual de Skype Empresarial y prepararlo para la próxima implementación de Microsoft Teams.   


### <a name="network-readiness-assessment"></a>Evaluación de preparación de la red


Debe realizar una *evaluación de preparación de la red* antes de implementar otros productos de comunicación en tiempo real, como Microsoft Teams. La *evaluación de preparación de la red* se centra en el rendimiento de la red, su planificación y otros aspectos generales relacionados con la red, como puertos y protocolos que deben estar abiertos. Incluso si está usando actualmente un producto de comunicaciones en tiempo real, como Skype Empresarial, la *evaluación de preparación de la red* le ayudará a validar cómo de preparada se encuentra su red.

Consiga la guía de [evaluación de preparación de la red](https://go.microsoft.com/fwlink/?linkid=859069).

### <a name="my-advisor"></a>My Advisor


Durante su recorrido, le recomendamos la guía práctica que encontrará en [My Advisor](http://aka.ms/myadvisor). My Advisor es una completa guía de autoservicio y un conjunto de herramientas que le ayudará a planificar y administrar correctamente todas las operaciones relacionadas con Microsoft Teams y Skype Empresarial Online.


### <a name="quality-assessment"></a>Evaluación de calidad


Antes de empezar a incorporar usuarios a Microsoft Teams, compruebe que su implementación actual de Skype Empresarial cumple con el nivel de calidad que se exige en lo referente a medios en tiempo real. Con el panel de calidad de llamadas (CQD, por su nombre en inglés "Call Quality Dashboard"), supervise el uso e identifique las tendencias de la calidad y, con el análisis de llamadas, preste atención a los indicadores de calidad de las llamadas individuales e intente resolver los problemas que encuentre.

Vea los [vídeos de CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos) para saber cómo debe usar el panel de calidad de llamadas para investigar la calidad de los medios.

Para obtener más información sobre el análisis de llamadas, vaya al tema relacionado con el [análisis de llamadas en Skype Empresarial](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-fbf7247a-84ae-46cc-9204-2c45b1c734cd).

### <a name="quality-champion-role"></a>Rol de experto de calidad


Los organizaciones deben identificar a una persona, o grupo de personas, a la que le adjudiquen el rol de experto en calidad. El experto en calidad se encarga de comparar las métricas de calidad con el uso y de identificar las tendencias en calidad y las áreas de mejora.

El experto en calidad se convertirá en la persona de referencia a la que se acudirá ante cualquier problema relacionado con la calidad y actuará como el experto en la materia para la identificación de problemas de calidad. Para ello se basará en la revisión del uso actual y las tendencias de calidad, así como la identificación de elementos de acción. El experto en calidad debe trabajar con los equipos correspondientes e impulsar acciones correctivas, informar al comité directivo sobre el progreso y abrir incidencias. El mejor candidato para ser experto en calidad es normalmente el propietario del servicio al cliente. Según sea el tamaño y la complejidad de la organización, cualquier persona a la que le apasione la experiencia de usuario y tenga las habilidades adecuadas para identificar tendencias puede actuar como experto en calidad. Contará con el respaldo necesario para poder trabajar con otros equipos y dirigir las correcciones que corresponda.

Consiga información sobre el concepto de experto en calidad y las herramientas y técnicas de revisión de calidad en el documento [Manage a quality and reliable service delivery workshop](https://go.microsoft.com/fwlink/?linkid=859071).

## <a name="environmental-dependencies"></a>Dependencias del entorno


Microsoft Teams combina varios servicios de Office 365 y, por lo tanto, depende de que estos servicios estén bien implementados y funcionen correctamente. Entre ellos encontramos, entre otros, SharePoint Online, Exchange Online y OneDrive para la Empresa.

Si bien no todos los servicios son necesarios, es muy recomendable que se implementen todos. Si decide no implementar algunos servicios, sepa que esta decisión podría influir en las funcionalidades que Microsoft Teams puede ofrecer a su organización. Por ejemplo, aunque no es obligatorio implementar SharePoint Online, Microsoft Teams sí se basa en SharePoint Online para llevar a cabo determinadas funciones, como compartir archivos en grupos. Si no implementa SharePoint Online, esta funcionalidad que se ofrece a través del cliente se verá afectada.

Vaya a los siguientes artículos para aprender más cosas sobre los requisitos:
- [Grupos de Office 365 y Microsoft Teams](Office-365-groups.md)
- [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](SharePoint-OneDrive-interact.md) 
- [Interacción entre Exchange y Microsoft Teams](Exchange-Teams-interact.md)



