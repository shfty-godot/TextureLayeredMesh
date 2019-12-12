# TextureLayeredMesh

TextureLayeredMesh is a wrapper class designed to make TextureLayered and its subclasses more editor-friendly.

It works around an engine bug that prevents TextureLayered subclasses (ex. TextureArray and Texture3D) from serializing their image layers.

This is done by serializing an array of layer data (Image, Texture or SpatialMaterial resources), then using it to recreate a TextureLayered subclass at runtime, which is then passed to a ShaderMaterialand applied to a MeshInstance. This MeshInstance is not added to the editor tree and will not be serialized, thus preventing unwanted error messages than can decrease editor performance with high texture counts.
