---
title: 'Lync Server 2013: Compatibilidad de Active Directory'
TOCTitle: Compatibilidad de Active Directory
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48274744
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad de Active Directory en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Las topologías de Servicios de dominio de Active Directory locales admitidas en Lync Server 2013 son las siguientes:

  - Un solo bosque con un solo dominio

  - Un solo bosque con un solo árbol y varios dominios

  - Un solo bosque con varios árboles y espacios de nombres separados

  - Varios bosques en una topología de bosque central

  - Varios bosques en una topología de bosque de recursos


> [!NOTE]
> Lync Server 2013 no admite dominios de etiqueta única. Por ejemplo, se admitiría un bosque con un dominio raíz denominado <STRONG>contoso.local</STRONG> pero no se admite un dominio raíz de etiqueta única denominada <STRONG>local</STRONG>. Para obtener más información, vea el artículo 300684 de Microsoft Knowledge Base, “Información acerca de la configuración de Windows para dominios con nombres DNS de etiqueta única”, en <A href="http://go.microsoft.com/fwlink/?linkid=143752%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=143752&amp;clcid=0xC0A</A>.




> [!NOTE]
> Lync Server 2013 no admite el cambio de nombre de dominio. Si necesita cambiar el nombre de un dominio en el que esté implementado Lync Server, desinstale primero Lync Server, después cambie el nombre del dominio y por último vuelva a instalar Lync Server.



Para obtener información sobre topologías admitidas y requisitos para implementaciones locales, vea [Topologías, compatibilidad y requisitos de los Servicios de dominio de Active Directory en Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) en la documentación sobre planeación.

