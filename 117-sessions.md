## Sessions

- Tüm sessionları listelemek : `Session::all();`
- Yeni bir session eklemek : `Session::put('name', 'Eylül');`
- Yeni bir session dizisine eleman eklemek : `Session::push('names', 'Mustafa');`
- Bir session anahtarına erişmek : `Session::get('name');`
- Tüm sessionları temizlemek : `Session::flush();`
- Sadece belli anahtardaki session'ı silmek : `Session::forget('surname');`

- Tek Request boyunca yaşayabilen session oluşturmak : `Session::flash('surname','Cankaya');`
- Tek request'lik session'u bir request daha yaşatmak : `Session::reflash('surname');`
