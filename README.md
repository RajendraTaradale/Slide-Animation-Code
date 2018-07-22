# Slide-Animation-Code

---------------------------
import { trigger, transition, state, animate, style, keyframes, useAnimation, query, animateChild, group, stagger } from '@angular/animations';

export const expandCollapse = trigger('expandCollapse', [
  state('collapsed', style({
    height: 0,
    paddingTop: 0,
    paddingBottom: 0,
    opacity: 0
  })),

  transition('collapsed => expanded', [
    animate('1000ms ease-in', style({
      height: '*',
      paddingTop: '*',
      paddingBottom: '*'
    })),
    animate('1s', style({ opacity: 1 }))
  ]),

  transition('expanded => collapsed', [
    animate('1000ms ease-in')
  ])
]);

----------------------------------------------
@Component({
  selector: 'app',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css'],
  providers: [AppService],
  animations : [expandCollapse]
})

 toggle(type:string) { 
       this.isExpandedaddress = !this.isExpandedaddress;
     }
---------------------------------

			  <accordion-group #dataPay  (isOpenChange)="toggleButton($event, 'payment')">
			  		<button class="btn btn-link btn-block clearfix" accordion-heading (click)="toggle()">
				      <div class="pull-left float-left"><span class="sequence">3</span> Payment Option</div>
				      <div class="pull-right float-right"><i id="paymentFaBtn" class="fa fa-plus"></i></div>
				    </button>
				    <div  class="payment-block" [@expandCollapse]="isExpandedpayment ? 'expanded' : 'collapsed'">
            Your content Here
            </div>
      </accordion>
      
      ---Thats it Done
