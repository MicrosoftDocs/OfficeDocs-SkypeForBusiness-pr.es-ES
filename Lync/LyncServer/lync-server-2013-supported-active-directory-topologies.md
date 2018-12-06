---
title: 'Lync Server 2013: Topologías admitidas de Active Directory'
TOCTitle: Topologías admitidas de Active Directory
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48274421
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologías admitidas de Active Directory en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Lync Server 2013 admite las mismas topologías de Servicios de dominio de Active Directory que Microsoft Lync Server 2010 y Microsoft Office Communications Server 2007 R2. Se admiten las siguientes topologías:

  - Un solo bosque con un solo dominio

  - Un solo bosque con un solo árbol y varios dominios

  - Un solo bosque con varios árboles y espacios de nombres separados

  - Varios bosques en una topología de bosque central

  - Varios bosques en una topología de bosque de recursos

  - Varios bosques en una topología de bosque de recursos de Lync con Exchange Online

En la siguiente figura se identifican los iconos utilizados en las ilustraciones de esta sección.

**Leyenda de las ilustraciones de topología**

![Leyenda de las ilustraciones de topología](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Leyenda de las ilustraciones de topología")

## Un solo bosque, un solo dominio

La topología de Active Directory más simple que Lync Server admite, un bosque de dominio único, es común.

En la siguiente figura se muestra una implementación de Lync Server en una topología de Active Directory de dominio único.

**Topología de dominio único**

![Topología de dominio único](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topología de dominio único")

## Un solo bosque, varios dominios

Otra topología de Active Directory admitida porLync Server es un bosque único que se compone de un dominio raíz y de uno o varios dominios secundarios. En este tipo de topología de Active Directory, el dominio donde se crean los usuarios puede ser diferente del dominio donde se implementaLync Server. Sin embargo, si implementa un grupo de servidores front-end, deberá implementar todos los servidores front-end del grupo en un dominio único. La compatibilidad de Lync Server con los grupos de administradores universales de Windows permite la administración entre dominios.

En la siguiente figura se muestra una implementación en un solo bosque con varios dominios. En esta figura, un icono de usuario muestra el dominio donde se hospeda la cuenta de usuario y la flecha apunta al dominio donde reside el grupo de servidores de Lync Server. Entre las cuentas de usuario se incluyen las siguientes:

  - Cuentas de usuario dentro del mismo dominio que el grupo de servidores de Lync Server

  - Cuentas de usuario en un dominio diferente al del grupo de servidores de Lync Server

  - Cuentas de usuario en un dominio secundario del dominio con el grupo de servidores de Lync Server

**Bosque único con varios dominios**

![Bosque único con varios dominios](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Bosque único con varios dominios")

## Un solo bosque, varios árboles

La topología de un solo bosque y varios árboles se compone de dos o más dominios que definen estructuras de árbol independientes y espacios de nombres de Active Directory independientes.

En la figura siguiente se muestra un solo bosque con varios árboles. En esta figura, un icono de usuario muestra el dominio donde se hospeda la cuenta de usuario, una línea continua señala a un grupo de servidores de Lync Server que reside en el mismo dominio o en otro diferente, y una línea con guiones señala al grupo de servidores de Lync Server que residen en un árbol distinto. Entre las cuentas de usuario se incluyen las siguientes:

  - Cuentas de usuario dentro del mismo dominio que el grupo de servidores de Lync Server

  - Cuentas de usuario de un dominio diferente al del grupo de servidores de Lync Server (pero con el mismo árbol)

  - Cuentas de usuario en un árbol diferente al del grupo de servidores de Lync Server

**Bosque único con varios árboles**

![Bosque único con varios árboles](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Bosque único con varios árboles")

## Varios bosques, bosque central

Lync Server admite varios bosques configurados en una topología de bosque central. Las topologías de bosque central utilizan objetos de contacto en el bosque central para representar a los usuarios en los otros bosques. El bosque central también hospeda las cuentas de usuario de cualquier usuario de este bosque. Un producto de sincronización de directorios, como, por ejemplo, Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), administra el ciclo de vida de las cuentas de usuario en la organización: cuando se crea una nueva cuenta de usuario en uno de los bosques o se elimina una cuenta de usuario de un bosque, el producto de sincronización de directorios sincroniza el contacto correspondiente en el bosque central.

Un bosque central tiene las ventajas siguientes:

  - Los servidores que ejecutan Lync Server están centralizados dentro de un solo bosque.

  - Los usuarios pueden buscar otros usuarios y comunicarse con ellos en cualquier bosque.

  - Los usuarios pueden ver la presencia de otros usuarios en cualquier bosque.

  - El producto de sincronización de directorios automatiza la adición y la eliminación de los objetos de contacto en el bosque central cuando se crean y se quitan cuentas de usuario.

En la figura siguiente se muestra una topología de bosque central. En esta figura, hay relaciones de confianza bidireccionales entre el dominio que hospeda Lync Server, que está en el bosque central, y cada uno de los dominios de solo usuarios, que están en un bosque independiente. No es preciso ampliar el esquema en los bosques de usuarios independientes.

**Topología de bosque central**

![Topología de bosque central](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topología de bosque central")

## Varios bosques, bosque de recursos

En una topología de bosque de recursos, uno de los bosques está dedicado a la ejecución de aplicaciones de servidor, como, por ejemplo, Microsoft Exchange Server y Lync Server. El bosque de recursos hospeda las aplicaciones de servidor y una representación sincronizada del objeto de usuario activo, pero no contiene cuentas de usuario habilitadas para el inicio de sesión. El bosque de recursos actúa como un entorno de servicios compartidos para los otros bosques donde residen objetos de usuario. Los bosques de usuarios tienen una relación de confianza en el nivel de bosque con el bosque de recursos. Al implementar Lync Server en este tipo de topología, se crea un objeto de usuario deshabilitado en el bosque de recursos para cada cuenta de usuario en los bosques de usuarios. Si ya se ha implementado Microsoft Exchange en el bosque de recursos, puede que ya existan las cuentas de usuario deshabilitadas. Un producto de sincronización de directorios, como, por ejemplo, MIIS, Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), administra el ciclo de vida de las cuentas de usuario en la organización: cuando se crea una nueva cuenta de usuario en uno de los bosques de usuarios o se elimina una cuenta de usuario de un bosque, el producto de sincronización de directorios sincroniza la correspondiente representación de usuario en el bosque de recursos.

Esta topología se puede usar para proporcionar una infraestructura compartida de los servicios en las organizaciones que administran varios bosques o para separar la administración de los objetos de Active Directory de otro tipo de administración. Las compañías que necesitan aislar la administración de Active Directory por razones de seguridad suelen elegir esta topología.

Esta topología aporta la ventaja de limitar la necesidad de extender el esquema de Active Directory a un solo bosque (es decir, el bosque de recursos).

En el diagrama siguiente se muestra una topología de bosque de recursos.

**Topología de bosque de recursos**

![Topología de bosque de recursos de Active Directory](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Topología de bosque de recursos de Active Directory")

## Varios bosques en una topología de bosque de recursos de Lync con Exchange Online

En esta topología, hay uno o más bosques ubicados localmente y dedicados a hospedar cuentas de usuario de Active Directory. El bosque de recursos no está ubicado localmente y lo mantiene un proveedor de hospedaje de terceros. El bosque de recursos solo contiene la implementación de Lync Server y una replicación sincronizada de las cuentas de usuario de los bosques de cuentas de usuario locales. No contiene cuentas de usuario habilitadas para el inicio de sesión. Exchange se implementa en los bosques de cuentas de usuario locales integrados junto con Exchange Online (implementación híbrida), o bien los servicios de correo electrónico de las cuentas de usuario locales los proporciona exclusivamente Exchange Online.

El bosque de recursos actúa como un entorno de servicios compartidos para los bosques de Active Directory locales donde residen los objetos de usuario. Los bosques de cuentas de usuario tienen una relación de confianza unidireccional en el nivel de bosque con el bosque de recursos. Al implementar Lync Server en este tipo de topología, crea en el bosque de recursos un objeto de usuario deshabilitado por cada cuenta de usuario de los bosques de usuarios. Un producto de sincronización de directorios, como MIIS, Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), administra el ciclo de vida de las cuentas de usuario. Cuando se crea una nueva cuenta de usuario en uno de los bosques de usuarios o cuando se elimina de un bosque una cuenta de usuario, el producto de sincronización de directorios sincroniza la representación del usuario correspondiente en el bosque de recursos. Para más información sobre cómo configurar una implementación de bosques múltiples, consulte el tema sobre [cómo implementar Lync en una arquitectura de bosques múltiples (Lync hospedado por un asociado con implementación híbrida de Exchange)](http://go.microsoft.com/fwlink/p/?linkid=513216).

