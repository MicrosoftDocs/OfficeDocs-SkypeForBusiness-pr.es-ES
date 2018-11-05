---
title: "Instalación de certificado en nodo de monitor localizado fuera de la red perimetral"
TOCTitle: "Install. d’un certif. sur un nœud observ. situé en dehors du réseau de périm."
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49889353
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalación de un certificado en un nodo de monitor localizado fuera de la red perimetral

 

_**Última modificación del tema:** 2016-12-08_

Los agentes de System Center Operations Manager que se ejecutan en una red perimetral (como un Lync Server servidor perimetral), fuera de la empresa (como un nodo de supervisión de transacción sintética externa) o en un límite de confianza Servicios de dominio de Active Directory, puede requerir la configuración de un servidor de puerta de enlace de System Center Operations Manager. Este rol de servidor permite que los agentes que no tienen una relación de confianza con el servidor de administración raíz inicien alertas. Para obtener detalles, vea "Administrar servidores de puerta de enlace en Operations Manager 2007" en la biblioteca TechNet de System Center Operations Manager en [http://go.microsoft.com/fwlink/?linkid=268703\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268703%26clcid=0xc0a).

Si implementa un agente en una de estas ubicaciones, también necesitará solicitar y configurar un certificado que habilite al nodo de supervisión enviar alertas a System Center Operations Manager. Para simplificar este proceso, el equipo de Operations Manager creó una serie de utilidades para que pueda solicitar e instalar el tipo correcto de certificado en la PC nodo de supervisión. Para obtener más detalles y para descargar estas utilidades, vea el artículo de blog "Obtener certificados para agentes no unidos al dominio fácilmente con el Asistente para generación de certificados" en [http://go.microsoft.com/fwlink/?linkid=267421\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=267421%26clcid=0xc0a).

