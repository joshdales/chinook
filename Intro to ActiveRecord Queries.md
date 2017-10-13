1.  Find the albums recorded by the artist Queen

irb(main):003:0> Artist.where("name = ?", "Queen")
  Artist Load (2.0ms)  SELECT  "artists".* FROM "artists" WHERE (name = 'Queen') LIMIT $1  [["LIMIT", 11]]
=> #<ActiveRecord::Relation [#<Artist id: 51, name: "Queen", created_at: "2006-01-08 22:57:01", updated_at: "2014-01-29 22:10:22">]>
irb(main):004:0> Albums.where(artist_name: "Queen")

irb(main):006:0> Album.where(artist_id: 51)
  Album Load (1.7ms)  SELECT  "albums".* FROM "albums" WHERE "albums"."artist_id" = $1 LIMIT $2  [["artist_id", 51], ["LIMIT", 11]]
=> #<ActiveRecord::Relation [#<Album id: 36, artist_id: 51, title: "Greatest Hits II", created_at: "2008-01-30 14:00:12", updated_at: "2014-01-29 22:14:02">, #<Album id: 185, artist_id: 51, title: "Greatest Hits I", created_at: "2007-12-29 12:02:13", updated_at: "2014-01-29 22:14:02">, #<Album id: 186, artist_id: 51, title: "News Of The World", created_at: "2010-06-23 20:50:06", updated_at: "2014-01-29 22:14:02">]>
