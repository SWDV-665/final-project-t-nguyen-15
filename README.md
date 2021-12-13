#login: tony@tony.com
#password: 123456

this login/password is stored in https://firebase.google.com/

JSON API = "https://orangevalleycaa.org/api/videos", the collection of activities in JSON which can convert to typescript, types.ts file:

export interface Activity {
    id: string;
    video_url: string;
    name: string;
    description: string;
    duration: string;
    created_by: string;
    image: string;
    thumbnail: string;
    cropped: string;
    file_name_original: string;
    popularity: string;
    category_id: string;
    category: string;
    keywords: string;
}

export interface LoginCredential {
    email: string;
    password: string;
}

I tried to store favorites on tab2.page.ts, but somehow it did not word on 2 comment lines bellow.
@Component({
  selector: 'app-tab2',
  templateUrl: 'tab2.page.html',
  styleUrls: ['tab2.page.scss']
})
export class Tab2Page {
  favoriteActivityList: Observable<any>;

  constructor(
    private _angularFireStore: AngularFirestore,
    private _angularFireAuth: AngularFireAuth
  ) {
    this.favoriteActivityList =  _angularFireStore
      .collection("favorites")
     //.doc(_angularFireAuth.currentUser.uid)
      //.collection("favorites")
      .valueChanges();
  }

}