---
title: "Autorizar la conexión al servidor perimetral de Office Communications Server 2007 R2"
TOCTitle: "Autor. de la connexion au serveur Edge Office Communications Server 2007 R2"
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48274521
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Autorizar la conexión al servidor perimetral de Office Communications Server 2007 R2

 

_**Última modificación del tema:** 2012-09-28_

Para cada servidor front-end de Lync Server 2013 o servidor Standard Edition de su grupo piloto, debe actualizar la lista de servidores internos autorizados para conectarse al servidor perimetral de Office Communications Server 2007 R2. Sin estas actualizaciones, no funcionará la conferencia de audio/vídeo (A/V) externa para los usuarios que se unen al servidor perimetral heredado.

## Para autorizar la conexión al servidor perimetral de Office Communications Server 2007 R2

1.  Desde el servidor perimetral de Office Communications Server 2007 R2, en el grupo **Herramientas administrativas**, abra el complemento **Administración de equipos**.

2.  En el árbol de consola, expanda **Servicios y aplicaciones**.

3.  Haga clic con el botón secundario en **Office Communications Server 2007 R2**y, a continuación, en **Propiedades**.

4.  Haga clic en la pestaña **Interno**.

5.  En **Agregar servidor**, haga clic en **Agregar**.

6.  En el cuadro de diálogo **Agregar Office Communications Server**, escriba la información pertinente:
    
      - Especifique el nombre de dominio completo (FQDN) de cada servidor front-end Lync Server 2013 o servidor Standard Edition y grupo de servidores de Lync Server 2013.
    
      - Especifique el FQDN del director de Lync Server 2013 si ha configurado una ruta estática en el grupo de servidores que especifica el equipo del próximo salto por su FQDN.

7.  Cuando haya agregado una entrada para cada Lync Server 2013, servidor front-end, servidor Standard Edition y Director, haga clic en **Aplicar** y, a continuación, en **Aceptar** para cerrar la página Propiedades.

