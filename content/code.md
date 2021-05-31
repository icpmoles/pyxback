---
title: Code TEST
codehl: false

---

Lorem ipsum dolor sit amet, consectetur adipiscing elit. In auctor tortor a enim placerat blandit. Nullam vehicula erat a erat vulputate, quis vulputate odio gravida. Nulla laoreet ullamcorper tempor. Fusce ultrices pellentesque tellus at pretium. Suspendisse viverra ex at ornare dignissim. Vivamus pulvinar quam ut dui volutpat, quis vestibulum mauris rhoncus. Aenean tempus, libero vitae efficitur varius, nunc velit sagittis tellus, non blandit orci ipsum rhoncus arcu. Vivamus egestas congue ultrices. Proin venenatis porttitor interdum. Vivamus diam sapien, aliquet sed ipsum quis, volutpat viverra arcu. Maecenas feugiat lectus ac felis convallis cursus.

{{< highlight C "linenos=inline">}}
static JsonbValue *
JsonbFromValue(JsonbParseState **pstate, Local<v8::Value> value, JsonbIteratorToken type) {
	Isolate *isolate = Isolate::GetCurrent();
	Local<Context>		context = isolate->GetCurrentContext();
	JsonbValue val;

	// if the token type is a key, the only valid value is jbvString
	if (type == WJB_KEY) {
		val.type = jbvString;
		String::Utf8Value utf8(isolate, value->ToString(context).ToLocalChecked());
		val.val.string.val = ToCStringCopy(utf8);
		val.val.string.len = utf8.length();
	} else {
		if (value->IsBoolean()) {
			val.type = jbvBool;
			val.val.boolean = value->BooleanValue(isolate);
		} else if (value->IsNull()) {
			val.type = jbvNull;
		} else if (value->IsUndefined()) {
			return NULL;
		} else if (value->IsString()) {
			val.type = jbvString;
			String::Utf8Value utf8(isolate, value->ToString(context).ToLocalChecked());
			val.val.string.val = ToCStringCopy(utf8);
			val.val.string.len = utf8.length();
		} else if (value->IsNumber()) {
			if (value->IsInt32()) {
				int32 iv = value->Int32Value(context).ToChecked();
				val.val.numeric = DatumGetNumeric(DirectFunctionCall1(int4_numeric, Int32GetDatum(iv)));
				val.type = jbvNumeric;
			} else if (value->IsUint32()) {
				int64 iv = (int64) value->Uint32Value(context).ToChecked();
				val.val.numeric = DatumGetNumeric(DirectFunctionCall1(int8_numeric, Int64GetDatum(iv)));
				val.type = jbvNumeric;
			} else {
				float8 fv = (float8) value->NumberValue(context).ToChecked();

				val.val.numeric = DatumGetNumeric(DirectFunctionCall1(float8_numeric, Float8GetDatum(fv)));
				val.type = jbvNumeric;
			}
		} else if (value->IsDate()) {
			double t = value->NumberValue(context).ToChecked();
			if (isnan(t)) {
				val.type = jbvNull;
			} else {
				val.val.string.val = TimeAs8601(t);
				val.val.string.len = 24;
				val.type = jbvString;
			}
		} else {
			LogType(value, false);
			val.type = jbvString;
			String::Utf8Value utf8(isolate, value->ToString(context).ToLocalChecked());
			val.val.string.val = ToCStringCopy(utf8);
			val.val.string.len = utf8.length();
		}
	}

	return pushJsonbValue(pstate, type, &val);
}{{< / highlight>}}

Lorem ipsum dolor sit amet, consectetur adipiscing elit. In auctor tortor a enim placerat blandit. Nullam vehicula erat a erat vulputate, quis vulputate odio gravida. Nulla laoreet ullamcorper tempor. Fusce ultrices pellentesque tellus at pretium. Suspendisse viverra ex at ornare dignissim. Vivamus pulvinar quam ut dui volutpat, quis vestibulum mauris rhoncus. Aenean tempus, libero vitae efficitur varius, nunc velit sagittis tellus, non blandit orci ipsum rhoncus arcu. Vivamus egestas congue ultrices. Proin venenatis porttitor interdum. Vivamus diam sapien, aliquet sed ipsum quis, volutpat viverra arcu. Maecenas feugiat lectus ac felis convallis cursus.


```
static JsonbValue *
JsonbFromValue(JsonbParseState **pstate, Local<v8::Value> value, JsonbIteratorToken type) {
	Isolate *isolate = Isolate::GetCurrent();
	Local<Context>		context = isolate->GetCurrentContext();
	JsonbValue val;

	// if the token type is a key, the only valid value is jbvString
	if (type == WJB_KEY) {
		val.type = jbvString;
		String::Utf8Value utf8(isolate, value->ToString(context).ToLocalChecked());
		val.val.string.val = ToCStringCopy(utf8);
		val.val.string.len = utf8.length();
	} else {
		if (value->IsBoolean()) {
			val.type = jbvBool;
			val.val.boolean = value->BooleanValue(isolate);
		} else if (value->IsNull()) {
			val.type = jbvNull;
		} else if (value->IsUndefined()) {
			return NULL;
		} else if (value->IsString()) {
			val.type = jbvString;
			String::Utf8Value utf8(isolate, value->ToString(context).ToLocalChecked());
			val.val.string.val = ToCStringCopy(utf8);
			val.val.string.len = utf8.length();
		} else if (value->IsNumber()) {
			if (value->IsInt32()) {
				int32 iv = value->Int32Value(context).ToChecked();
				val.val.numeric = DatumGetNumeric(DirectFunctionCall1(int4_numeric, Int32GetDatum(iv)));
				val.type = jbvNumeric;
			} else if (value->IsUint32()) {
				int64 iv = (int64) value->Uint32Value(context).ToChecked();
				val.val.numeric = DatumGetNumeric(DirectFunctionCall1(int8_numeric, Int64GetDatum(iv)));
				val.type = jbvNumeric;
			} else {
				float8 fv = (float8) value->NumberValue(context).ToChecked();

				val.val.numeric = DatumGetNumeric(DirectFunctionCall1(float8_numeric, Float8GetDatum(fv)));
				val.type = jbvNumeric;
			}
		} else if (value->IsDate()) {
			double t = value->NumberValue(context).ToChecked();
			if (isnan(t)) {
				val.type = jbvNull;
			} else {
				val.val.string.val = TimeAs8601(t);
				val.val.string.len = 24;
				val.type = jbvString;
			}
		} else {
			LogType(value, false);
			val.type = jbvString;
			String::Utf8Value utf8(isolate, value->ToString(context).ToLocalChecked());
			val.val.string.val = ToCStringCopy(utf8);
			val.val.string.len = utf8.length();
		}
	}

	return pushJsonbValue(pstate, type, &val); 
```

Maecenas vel ex tempor, laoreet mauris sit amet, dapibus nunc. Suspendisse potenti. In tempor metus molestie, elementum nisl sed, viverra quam. Mauris auctor dolor tortor, sit amet sodales nisl blandit eget. Nulla tristique rhoncus euismod. Ut scelerisque, tellus sed posuere pretium, lectus quam euismod nibh, id dignissim arcu enim ac ligula. Morbi finibus efficitur neque, a pellentesque sapien rhoncus molestie. Maecenas et purus non arcu sagittis efficitur. Donec quis placerat sem.

