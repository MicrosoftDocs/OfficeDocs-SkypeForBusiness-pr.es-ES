---
title: "Sustituir XmlAdapter con adaptador de cumplimiento para servidor de chat persistente"
TOCTitle: "Rempl. XmlAdapter par ad. de conf. perso. du serv. de conv. perm. dans LS 2013"
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49889021
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sustitución de XmlAdapter con un adaptador de cumplimiento para servidores de chat persistente personalizado en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Puede escribir un adaptador personalizado en lugar de utilizar el XmlAdapter que se instala con Servidor de chat persistente. Para lograr esto, debe brindar un ensamblado de .NET Framework que contenga una clase pública que implemente la interfaz de **IComplianceAdapter**. Debe colocar este ensamblado en la carpeta de instalación de Servidor de chat persistente de cada servidor de su Grupo de servidores de chat persistente. Cualquiera de los servidores de Cumplimiento puede brindar datos de cumplimiento para su adaptador, pero los servidores de cumplimiento no brindarán datos de cumplimiento duplicados a varias instancias de su adaptador.

## Implementación de la interfaz de IComplianceAdapter

La interfaz se define en el ensamblado Compliance.dll en el espacio de nombres `Microsoft.Rtc.Internal.Chat.Server.Compliance`. La interfaz define dos métodos que su adaptador personalizado debe implementar.

    void SetConfig(AdapterConfig config)

El servidor de Cumplimiento de Chat persistente llamará a este método cuando se cargue el adaptador por primera vez. El `AdapterConfig` contiene la configuración de cumplimiento de Chat persistenteque es relevante para el adaptador de cumplimiento.

    void Translate(ConversationCollection conversations)

l servidor de Cumplimiento de Chat persistente invoca este método en intervalos periódicos siempre que haya nuevos datos para traducir. Este intervalo es igual al `RunInterval` según se lo haya definido en la configuración de Cumplimiento de Chat persistente.

La `ConversationCollection` contiene la información de conversación que se recopiló de la última vez que se invocó este método.

