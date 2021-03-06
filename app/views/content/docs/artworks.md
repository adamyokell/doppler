[Documentation](/docs) &gt; Resources &gt; Artworks

## Artworks API

An artwork is an artistic production created by an [artist](/docs/artists), multiple artists or an artist collective. An artwork may be part of a series and be reproduced in prints. Artworks are available from Artsy [partners](/docs/partners).

#### Retrieving Artworks

Retrieve artworks by following the [artworks](#{ArtsyAPI.artsy_api_root}/artworks) link from [root](#{ArtsyAPI.artsy_api_root}).

```
curl -v "#{ArtsyAPI.artsy_api_root}/artworks?public=true" -H "X-XAPP-Token:#{xapp_token}"
```

This endpoint accepts the following parameters.

Name       | Value                                                             |
----------:|:------------------------------------------------------------------|
public     | Retrieve publicly available artworks. This is currently required. |

The response is a [paginated result](/docs/pagination) with embedded artworks.

#### Retrieving an Artwork

Users can retrieve a specific artwork by ID by rendering the "artwork" link template from [root](#{ArtsyAPI.artsy_api_root}).

```
curl -v "#{ArtsyAPI.artsy_api_root}/artworks/{id}" -H "X-XAPP-Token:#{xapp_token}"
```

## Artwork JSON Format

#{modelref://Artwork}

#### Links

Key        | Target                                           |
----------:|:-------------------------------------------------|
self       | The artwork resource.                            |
thumbnail  | Default image thumbnail.                         |
image:self | Curied image location.                           |
permalink  | An external location on the artsy.net website.   |
partner    | [Partner](/docs/partners) that owns the artwork. |

#### Embedded Collections

Key           | Target                                                                          |
-------------:|:--------------------------------------------------------------------------------|
artist_links  | A set of links to the [artists](/docs/artists) of this artwork.                 |
edition_sets  | A set of artwork [edition sets](/docs/edition_set) available for this artwork.  |

#### Example

``` json
#{resource://artwork/id=4d8b92c34eb68a1b2c000496}
```
