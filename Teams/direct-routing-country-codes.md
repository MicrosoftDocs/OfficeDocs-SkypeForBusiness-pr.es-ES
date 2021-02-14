---
title: Códigos de país de enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lea este artículo para localizar los códigos de país de la ruta multimedia de enrutamiento directo para que pueda seleccionar la ruta de acceso a medios óptima.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69265e797b256186f714e2cd4dcefcb3751c05ee
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904812"
---
# <a name="direct-routing-media-path-country-codes"></a>Códigos de país de ruta de acceso directo a medios

Al elegir una ruta de enrutamiento para medios, enrutamiento directo, de forma predeterminada, siempre asigna un centro de datos según la dirección IP pública del controlador de borde de sesión (SBC) y siempre selecciona la ruta más cercana al centro de datos SBC.

Sin embargo, en algunos casos, la ruta de acceso a medios predeterminada puede no ser la ruta de medios óptima; por ejemplo, una IP pública de un rango de Estados Unidos podría asignarse a una SBC ubicada en Europa. 

Mediante el parámetro -MediaReroutingLocationOverride con los cmdlets New-CsOnlinePSTNGateway y Set-CsOnlinePSTNGateway, puede especificar la región preferida para el tráfico multimedia. Por ejemplo, el siguiente comando especifica que la región preferida es Alemania:

Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com –MediaReroutingLocationOverride DE 

Tenga en cuenta que Microsoft solo recomienda configurar este parámetro si los registros de llamada indican claramente que la asignación predeterminada del centro de datos para la ruta de acceso multimedia no usa la ruta más cercana al centro de datos SBC. 
 
## <a name="country-code-reference-table"></a>Tabla de referencia de código de país

En la tabla siguiente se muestran los valores de código de país para el parámetro -MediaReroutingLocationOverride:

| País         | Código 
|-----------------|--------------------|
| Afganistán     | AF |
| Islas Land   | AX |
| Albania         | AL |
| Argelia         | DP |
| Samoa Americana  | AS |
| Andorra         | AD |
| Angola          | AO |
| Anguila        | IA |
| Antártida      | AQ | 
| Antigua y Barbuda | AG |
| Argentina       | AR |
| Armenia         | AM |
| Aruba           | AW |
| Australia       | AU |
| Austria         | AT |
| Azerbaiyán      | AZ |
| Bahamas         | BS |
| Baréin         | ABS |
| Bangladesh      | BD |
| Barbados        | BB |
| Belarús         | BY |
| Bélgica         | BE |
| Belice          | BZ |
| Benín           | BJ |
| Bermudas         | BM |
| Bután          | BT |
| Bolivia         | BO |
| Bonaire         | BQ |
| Bosnia y Herzegovina | BA |
| Botsuana        | BW |
| Isla Bouvet   | BALL |
| Brasil          | BR |
| Territorio Británico del Océano Índico | IO |
| Islas Vírgenes Británicas | DVS |
| Brunéi          | BN |
| Bulgaria        | BG |
| Burkina Faso    | BF |
| Burundi         | BI |
| Cabo Verde      | CV |
| Camboya        | KH |
| Camerún        | CM |
| Canada          | CA |
| Islas Caimán  | KY |
| República Centroafricana | CF |
| Chad            | TD |
| Chile           | CL |
| China           | CN |
| Isla Christmas | CX |
| Islas Cocos (Keeling) | CC |
| Colombia        | CO |
| Comoras         | KM |
| Congo           | GC |
| Congo (RDC)     | CD |
| Islas Cook    | CK |
| Costa Rica      | CR |
| Costa de Ivoire   | CI |
| Croacia         | RR. HH. |
| Cuba            | CU |
| Curazao         | CW |
| Chipre          | CY |
| Chequia         | CZ |
| Dinamarca         | DK |
| Yibuti        | DJ |
| Dominica        | DM |
| República Dominicana | DO |
| Ecuador         | EC |
| Egipto           | EG |
| El Salvador     | SV |
| Guinea Ecuatorial | GQ |
| Eritrea         | EMERGENCIA |
| Estonia         | EE |
| Eswawawa        | SZ |
| Etiopía        | ET |
| Islas Malvinas | CE |
| Islas Feroe   | FO |
| Fiyi            | FJ |
| Finlandia         | FI |
| Francia          | FR |
| Guayana Francesa   | GF |
| Polinesia Francesa | PF |
| Territorios Australes Franceses | TF |
| Que ha estado en el mismo lugar           | GA |
| Gambia          | GM |
| Georgia         | GE |
| Alemania         | DE |
| Ghana           | GH |
| Gibraltar       | GI |
| Grecia          | GR |
| Groenlandia       | GL |
| Granada         | GD |
| Guadalupe      | GP |
| Guam            | GU |
| Guatemala       | GT |
| Guernsey        | GG |
| Guinea          | GN |
| Guinea-Bissau   | GW |
| Guyana          | YES |
| Haití           | HI |
| Islas Heard y McDonald | HM |
| Honduras        | HN |
| RAE de Hong Kong   | HK |
| Hungría         | HU |
| Islandia         | ES |
| India           | IN |
| Indonesia       | ID |
| Irán            | IR |
| Irak            | IQ |
| Irlanda         | IE |
| Isla de Man     | MI |
| Israel          | IL |
| Italia           | IT |
| Jamaica         | JM |
| Jan Mayen       | XJ |
| Japón           | JP |
| Jersey          | JE |
| Jordania          | JO |
| Kazajistán      | KZ |
| Kenia           | KE |
| Kiribati        | KI |
| Corea           | KR |
| Kosovo          | XK |
| Kuwait          | KW |
| Kirguistán      | KG |
| Laos            | LA |
| Letonia          | LV |
| Líbano         | LB |
| Lesoto         | LS |
| Según se ha des         | LR |
| Libia           | LY |
| Liechtenstein   | LI |
| Lituania       | LT |
| Luxemburgo      | LU |
| RAE de Macao       | MO |
| Madagascar      | MG |
| Malaui          | VAT |
| Malasia        | MY |
| Maldivas        | MV |
| Mali            | ML |
| Malta           | MT |
| Islas Marshall | MH |
| Martinica      | INSC |
| Mauritania      | MR |
| Mauricio       | MU |
| Mayotte         | YT |
| México          | MX |
| Micronesia      | FM |
| Moldova         | MD |
| Mónaco          | MC |
| Mongolia        | MN |
| Montenegro      | ME |
| Montserrat      | MS |
| Marruecos         | MA |
| Mozambique      | MZ |
| Myanmar         | MM |
| Namibia         | NA |
| Nauru           | NR |
| Nepal           | NP |
| Países Bajos     | NL |
| Nueva Caledonia   | NC |
| Nueva Zelanda     | NZ |
| Nicaragua       | NI |
| Níger           | NE |
| Nigeria         | NG |
| Niue            | NU |
| Isla Nor insular  | NF |
| Corea del Norte     | KP |
| Macedonia del Norte | MK |
| Islas Marianas del Norte | NP |
| Noruega          | No |
| Omán            | OM |
| Pakistán        | PK |
| Palaos           | PW |
| Autoridad Nacional Palestina | PS |
| Panamá          | PA |
| Guinea Ecuatorial | PG |
| Paraguay        | PY |
| Perú            | PE |
| Filipinas     | PH |
| Islas Pitcairn | PN |
| Polonia          | PL |
| Portugal        | PT |
| Puerto Rico     | PR |
| Catar           | QA |
| Reunión         | RE |
| Rumania         | RO |
| Rusia          | RU |
| Ruanda          | RW |
| Saba            | XS |
| San Bartolomé | BL |
| San Cristóbal y Nieves | KN |
| Santa Lucía     | LC |
| San Martín    | INSONY |
| San Pedro y Miquelón | PM |
| San Vicente y las Granadinas | VC |
| Samoa           | WS |
| San Marino      | SM |
| Santo Tomé y Príncipe | ST |
| Arabia Saudí    | SA |
| Senegal         | SN |
| Serbia          | RS |
| Seychelles      | SC |
| Sierra Leona    | SL | 
| Singapur       | SG |
| San Eustaquio  | XE |
| Sint Maarten    | SX |
| Eslovaquia        | SK |
| Eslovenia        | SL |
| Islas Salomón | SB |
| Somalia         | SO |
| Sudáfrica    | ZA |
| Georgia del Sur e Islas Sandwich del Sur | GS |
| Sudán del Sur     | SS |
| España           | ES |
| Sri Lanka       | LK |
| Santa Elena, Ascensión y Tristán da Cunha | SH |
| Sudán           | SD |
| Surinam        | SR |
| Svalbard        | SJ |
| Suecia          | SE |
| Suiza     | CH |
| Siria           | SY |
| Taiwán          | TW |
| Tayikistán      | TJ |
| Tanzania        | TZ |
| Tailandia        | TH |
| Timor-Leste     | TL |
| Togo            | TG |
| Tokelau         | TK |
| Tonga           | Para |
| Trinidad y Tobago | TT |
| Túnez         | TN |
| Turquía          | TR |
| Turkmenistán    | TM |
| Islas Turcas y Caicos | TC |
| Tuvalu          | TELEVISIÓN |
| Islas No Cercanas de EE. UU. | UM |
| Islas Vírgenes de LOS EE. UU. | VI |
| Uganda          | UG |
| Ucrania         | UA |
| Emiratos Árabes Unidos | AE |
| Reino Unido  | GB |
| Estados Unidos   | EE. UU. |
| Uruguay         | UY |
| Uzbekistán      | UZ |
| Vanuatu         | VU |
| Ciudad del Vaticano    | VA |
| Venezuela       | VE |
| Vietnam         | VN |
| Wallis y Futuna | WF |
| Yemen           | YE |
| Zambia          | ZM |
| Zimbabue        | ZW |

