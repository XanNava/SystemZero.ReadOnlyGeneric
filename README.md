This is intended to be used so the fact of you passing a read only value is known throughout your code. This way it can be requested and generated as needed, but people don't think they can edit it.

```cs
protected ReadOnly<T> _CachedValue;
		
// TODO : Move to file.
public struct ReadOnly<T> {
  public readonly T value;

  public ReadOnly(T value) {
    this.value = value;
  }
}


Usage

protected ReadOnly<T> _CachedValue { get { /* if dirty re calnculate value.} }

protected bool _dirty;
protected virtual bool _Dirty {
  get {
    return _dirty;
  }
  set {
    if (value) {
      _dirty = true;
    }
    _dirty = false;
  }
}
```
